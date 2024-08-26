<template>
    <div class="row">
        <div class="col-md-5">
            <div class="border border-1 border-success p-2">
                <div class="shadow p-2 mb-5 rounded text-black" style="background-color: #B2D6F4;">
                    <h5>Avtomobil xaridi</h5>
                    Savol 1 / 2
                </div>

                <div class="btn-group w-100">
                    <button class="btn btn-secondary btn-sm dropdown-toggle" type="button" data-bs-toggle="dropdown"
                        aria-expanded="false">
                        Narx hisoblagichdan foydalanish
                    </button>
                    <ul class="dropdown-menu p-1">
                        <p>Narx hisoblagich avtomobil xarid qilish va birinchi yili foydalanish uchun qancha xarajat
                            bo'lishini aniqlaydi.</p><br>
                        <p>Hisoblagichdan foydalanish uchun, quyidagi bosqichlarga rioya qiling:</p>

                        <ol>
                            <li>Avtomobil narxini kiriting.</li>
                            <li>Yoq'ilg'i sarfini kiriting.</li>
                            <li>"Hisoblash" tugmasini bosing. Natija Natijalar jadvalida ko'rsatiladi.</li>
                            <li>Qo'shimcha hisoblashlarni olib borish uchun,"Tozalash" tugmasini bosing, yangi
                                qiymatlarni kiriting va yana "Hisoblash" tugmasini bosing. </li>
                        </ol>

                        <p><i class="fa fa-exclamation-triangle"></i> Natijalar jadvalidan biror ma'lumotlar qatorini
                            o'chirish uchun, o'sha qator yonidagi o'chirich tugmasini bosing.</p>
                    </ul>
                </div>
                <br>
                <i>O'ng tomondagi "Avtomobil xaridi" ga qarang. Quyidagi savolga javob berish uchun Narx hisoblagichdan
                    foydalaning. Savolga javob berish uchun tanlovingiz ustiga bosing.</i>
                <br><br>
                <p>Narx hisoblagichdan qanday foydalanishni ko'rish uchun yuqoridagi "Narx hisoblagichdan foydalanish"
                    ni bosing.</p>
                <br>
                <p>Tanzilaning hisob-kitoblariga asoslanib, qaysi avtomobilni xarid qilish va birinchi yil foydalanishi
                    <b>eng arzon</b>ga tushadi?</p>
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

            <p>Tanzila xarid qilish uchun ko'rib chiqayotgan to'rtta avtomobilning narxlari va yoqilg'i sarfi quyidagi
                jadvalda ko'rsatilgan.</p>
            <p>Yoqilg'i sarfi - bu 100 kilometr masofani bosib o'tish uchun zarur bo'lgan yoqilg'ining litr miqdoridir.
                Bu shahar bilan birga avtomagistralda haydashga asoslangan holda taxminan hisoblanadi.</p>

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

            <br>
            <p>Narx hisoblagichning ba'zi katakchalari Tamaraning hisob-kitoblariga asoslanib to'ldirilgan.</p>

            <div class="row">
                <div class="col-md-9">
                    <div>
                        <h6 class="text-center m-2">NARX HISOBLAGICH</h6>

                        <form class="p-3" @submit.prevent="calculateCost">
                            <div class="mb-3 row">
                                <label for="carPrice" class="col-sm-6 col-form-label">Avtomobil narxi (zedlarda)</label>
                                <div class="col-sm-6">
                                    <input type="number" v-model="carPrice" class="form-control" id="carPrice" required>
                                </div>
                            </div>
                            <div class="mb-3 row">
                                <label for="fuelConsumption" class="col-sm-6 col-form-label">Yoqlig'i sarfi (L/100
                                    km)</label>
                                <div class="col-sm-6">
                                    <input type="number" v-model="fuelConsumption" class="form-control"
                                        id="fuelConsumption" required>
                                </div>
                            </div>
                            <div class="mb-3 row">
                                <label for="distance" class="col-sm-6 col-form-label">Taxminiy bosib o'tilgan masofa
                                    (km)</label>
                                <div class="col-sm-6">
                                    <input type="number" v-model="distance" class="form-control" id="distance" disabled>
                                </div>
                            </div>
                            <div class="mb-3 row">
                                <label for="fuelPrice" class="col-sm-6 col-form-label">Yoqlig'ining o'rtacha narxi
                                    (zed/L)</label>
                                <div class="col-sm-6">
                                    <input type="number" v-model="fuelPrice" class="form-control" id="fuelPrice"
                                        disabled>
                                </div>
                            </div>
                            <div class="mb-3 row">
                                <label for="serviceCost" class="col-sm-6 col-form-label">Taxminiy texnik xizmat
                                    ko'rsatish
                                    narxlari
                                    (zedlarda)</label>
                                <div class="col-sm-6">
                                    <input type="number" v-model="serviceCost" class="form-control" id="serviceCost"
                                        disabled>
                                </div>
                            </div>
                            <div class="d-flex justify-content-between">
                                <button type="reset" class="btn btn-danger">O'chirish</button>
                                <button type="submit" class="btn btn-success">Hisoblash</button>
                            </div>
                        </form>
                    </div>
                </div>

                <div class="col-md-3">
                    <h6 class="bg-secondary text-center text-white p-2">NATIJALAR</h6>

                    <table class="table-striped">
                        <tbody>
                            <tr>
                                <td>...</td>
                            </tr>
                            <tr>
                                <td>...</td>
                            </tr>
                            <tr>
                                <td>...</td>
                            </tr>
                            <tr>
                                <td>...</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </div>
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