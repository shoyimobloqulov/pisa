<template>
  <div class="container">
    <div class="alert alert-primary alert-dismissible fade show shadow-sm bg-body rounded" role="alert">
      <strong>Avtomobil xaridi!</strong> Kirish.
      <button type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Close"></button>
    </div>

    <i>Kirishni o'qing. So'ngra <b>KEYINGI</b> tugmasini bosing. </i>

    <div class="border border-1 border-primary p-3 shadow-sm bg-body rounded">
      <h5 class="text-center m-4">AVTOMOBIL XARIDI</h5>

      <p>Tanzila yangi avtomobil xarid qilishni rejalashtirmoqda. U yangi avtomobilni xarid qilish va undan birinchi
        yili foydalanish xarajatlarini bilmoqchi.</p>

      <br>
      <div class="row d-flex align-items-center">
        <div class="col-md-6">
          <div class="">
            <p>U internetdan mazkur Narx hisoblagichni topdi va quyidagi hisoblashlarni amalga oshirdi:</p>
            <ul>
              <li>U bu yilda taxminan 20 000 km masofani bosib o'tmoqchi.</li>
              <li>Yoqilg'ining o'rtacha narxi har bir litr uchun 1,54 zed bo'ladi.</li>
              <li>Taxminiy texnik xizmat ko'rsatish narxlari birinchi yilda 250 zed bo'ladi.</li>
            </ul>
          </div>
        </div>
        <div class="col-md-6">
          <div class="border border-2 border-second bg-light bg-gradient">
            <h6 class="text-center m-2">NARX HISOBLAGICH</h6>

            <form class="p-3" @submit.prevent="calculateCost">
              <div class="mb-3 row">
                <label for="carPrice" class="col-sm-6 col-form-label">Avtomobil narxi (zedlarda)</label>
                <div class="col-sm-6">
                  <input type="number" v-model="carPrice" class="form-control" id="carPrice" required>
                </div>
              </div>
              <div class="mb-3 row">
                <label for="fuelConsumption" class="col-sm-6 col-form-label">Yoqlig'i sarfi (L/100 km)</label>
                <div class="col-sm-6">
                  <input type="number" v-model="fuelConsumption" class="form-control" id="fuelConsumption" required>
                </div>
              </div>
              <div class="mb-3 row">
                <label for="distance" class="col-sm-6 col-form-label">Taxminiy bosib o'tilgan masofa (km)</label>
                <div class="col-sm-6">
                  <input type="number" v-model="distance" class="form-control" id="distance" required>
                </div>
              </div>
              <div class="mb-3 row">
                <label for="fuelPrice" class="col-sm-6 col-form-label">Yoqlig'ining o'rtacha narxi (zed/L)</label>
                <div class="col-sm-6">
                  <input type="number" v-model="fuelPrice" class="form-control" id="fuelPrice" required>
                </div>
              </div>
              <div class="mb-3 row">
                <label for="serviceCost" class="col-sm-6 col-form-label">Taxminiy texnik xizmat ko'rsatish narxlari
                  (zedlarda)</label>
                <div class="col-sm-6">
                  <input type="number" v-model="serviceCost" class="form-control" id="serviceCost" required>
                </div>
              </div>
              <div class="d-flex justify-content-between">
                <button type="reset" class="btn btn-danger">O'chirish</button>
                <button type="submit" class="btn btn-success">Hisoblash</button>
              </div>
            </form>

            <div v-if="totalCost !== null" class="mt-4 alert alert-info m-2">
              Umumiy xarajat: {{ totalCost }} zed
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        carPrice: 0,
        fuelConsumption: 0,
        distance: 20000, // as per the example scenario
        fuelPrice: 1, // as per the example scenario
        serviceCost: 250, // as per the example scenario
        totalCost: null
      }
    },

    methods: {
      calculateCost() {
        const fuelCost = (this.distance / 100) * this.fuelConsumption * this.fuelPrice;
        this.totalCost = this.carPrice + fuelCost + this.serviceCost;
      }
    }
  }
</script>