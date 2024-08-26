<template>
    <div class="row">
        <div class="col-md-5">
            <div class="border border-1 border-success p-2">
                <div class="shadow p-2 mb-5 rounded text-black" style="background-color: #B2D6F4;">
                    <h5>Avtomobil xaridi</h5>
                    Savol 2 / 2
                </div>
  
                <i>O'ng tomondagi "Avtomobil xaridi" ga qarang. Quyidagi savolga javob berish uchun Narx hisoblagichdan
                    foydalaning. Savolga javob berish uchun tanlovingiz ustiga bosing.</i>
                <br><br>
                <p>Avtomobilning <b>qayta sotilish narxi</b> keyinchalik u qayta sotilishi mumkin bo'lgan taxminiy narxidir.</p>
                <br>
                <p>Yaxshi holatda saqlanadigan avtomobil uchun, uning qayta sotilish narxi har yili 5% kamayadi.</p>

                <p>Agar Tanzila D avtomobilni xarid qilmoqchi bo'lsa va uni yaxshi holatda uch yildan keyin qaytarib sotsa, avtomobilning zedlardagi taxminiy qayta sotilish narxi qancha bo'ladi?</p>
            </div>

            <div class="form-group m-2">
                <div>
                    <input type="radio" id="q2a" name="question2" value="A">
                    <label for="q2a">A avtomobil</label>
                </div>
                <div>
                    <input type="radio" id="q2b" name="question2" value="B">
                    <label for="q2b">B avtomobil</label>
                </div>
                <div>
                    <input type="radio" id="q2c" name="question2" value="C">
                    <label for="q2c">C avtomobil</label>
                </div>

                <div>
                    <input type="radio" id="q2c" name="question2" value="C">
                    <label for="q2c">D avtomobil</label>
                </div>
            </div>
        </div>

        <div class="col-md-7">
            <h5 class="text-center">AVTOMOBIL XARIDI</h5>

            <p>Tanzila xarid qilish uchun ko'rib chiqayotgan to'rtta avtomobilning narxlari va yoqilg'i sarfi quyidagi jadvalda ko'rsatilgan.</p>
            <p>Yoqilg'i sarfi - bu 100 kilometr masofani bosib o'tish uchun zarur bo'lgan yoqilg'ining litr miqdoridir. Bu shahar bilan birga avtomagistralda haydashga asoslangan holda taxminan hisoblanadi.</p>

            <table class="table">
                <thead>
                    <tr>
                        <th scope="col"></th>
                        <th scope="col">A avtomobil</th>
                        <th scope="col">B avtomobil</th>
                        <th scope="col">C avtomobil</th>
                        <th scope="col">D avtomobil</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td scope="row">
                            <b>Avtomobil narxi </b>(zedlarda)
                            Avtomobil narxi barcha soliqlar va ro'yxatdan o'tkazish to'lovlarini o'z ichiga oladi.
                        </td>
                        <td>8000</td>
                        <td>8700</td>
                        <td>9900</td>
                        <td>10 500</td>
                    </tr>
                    <tr>
                        <td scope="row">
                            <b>Yoqilg'i sarfi</b>
                            (L/100 km)
                        </td>
                        <td>18,9</td>
                        <td>15,7 </td>
                        <td>12,4 </td>
                        <td>14,1</td>
                    </tr>
                </tbody>
            </table>
        </div>

        
    </div>
    <button class="btn btn-primary float-end mt-5">Testni tugalash</button>
</template>

<style scoped>
    input {
        margin: 5px;
    }
</style>

<script>
    export default {
        data() {
            return {
                carPrice: 0,
                fuelConsumption: 0,
                distance: 20000, // as per the example scenario
                fuelPrice: 1.54, // as per the example scenario
                serviceCost: 250, // as per the example scenario
                totalCost: null
            }
        },
    }
</script>