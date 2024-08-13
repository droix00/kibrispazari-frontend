<template>
    <div class="container">
        <div class="kutu1">
            YATIRIM AMAÇLI YÜKSEK KİRA GETİRİLİ TEMİZ DAİRE
        </div>
        <hr />
        <div class="kutu2">
            <div v-for="resim in vitrinResim.slice(0, 1)" :key="resim.id" class="ana-resim">
                <img :src="resim.image" alt="Resim">
            </div>
            <div v-for="resim in vitrinResim.slice(1, 13)" :key="resim.id" class="mini-resimler">
                <img :src="resim.image" alt="Resim">
            </div>
        </div>
        <!-- SADECE MOBİL İÇİN GÖRÜNECEK KODLAR BAŞLANGIÇ -->
        <div class="mobil-degisken-icerik hidden flex text-center">
            <div class="baslik1 bg-slate-700 text-white ml-2 p-2">İlan Bilgileri</div>
            <div class="baslik2 border border-slate-300 ml-2 p-2">Açıklama</div>
            <div class="baslik2 border border-slate-300 ml-2 mr-2 p-2">Konumu</div>
        </div>
        <!-- SADECE MOBİLDE GÖRÜNECEK KODLARIN BİTİŞİ -->
        <div class="kutu3">

            <div class="flex justify-between items-center">
                <div class="ilan_fiyat text-[1.2rem] font-medium text-[#059]">3.600.000 TL</div>
                <div class="ilan_fav_ekle text-[1.2rem] font-medium text-[#059]"><i class="fa-regular fa-star active:bg-sky-700"></i></div>
            </div>
            <div class="ilan_konum">Lefkoşa / Gönyeli</div>
            <table class="min-w-full mt-2">
                <thead class="">
                    <tr class="mobilde-gorunecek-fiyat md:hidden">
                        <td class="sol-metin text-left border-b border-gray-200">İlan Fiyat </td>
                        <td class="sag-metin text-right text-rose-800 font-medium border-b border-gray-200">3.600.000 TL
                        </td>
                    </tr>
                    <tr>
                        <td class="sol-metin text-left border-b border-gray-200">İlan No </td>
                        <td class="sag-metin text-right text-rose-800 border-b border-gray-200">54253148</td>
                    </tr>
                    <tr>
                        <td class="sol-metin text-left border-b border-gray-200">İlan Tarihi</td>
                        <td class="sag-metin text-right border-b border-gray-200">24 Ocak 2024</td>
                    </tr>
                    <tr>
                        <td class="sol-metin text-left border-b border-gray-200">Emlak Tipi</td>
                        <td class="sag-metin text-right border-b border-gray-200">Kiralık Daire</td>
                    </tr>
                    <tr>
                        <td class="sol-metin text-left border-b border-gray-200">m² Brüt</td>
                        <td class="sag-metin text-right border-b border-gray-200">214</td>
                    </tr>
                    <tr>
                        <td class="sol-metin text-left border-b border-gray-200">m² Net</td>
                        <td class="sag-metin text-right border-b border-gray-200">190</td>
                    </tr>
                    <tr>
                        <td class="sol-metin text-left border-b border-gray-200">Oda Sayısı</td>
                        <td class="sag-metin text-right border-b border-gray-200">5+1</td>
                    </tr>
                    <tr>
                        <td class="sol-metin text-left border-b border-gray-200">Bulunduğu Kat</td>
                        <td class="sag-metin text-right border-b border-gray-200">2</td>
                    </tr>
                    <tr>
                        <td class="sol-metin text-left border-b border-gray-200">Kat Sayısı</td>
                        <td class="sag-metin text-right border-b border-gray-200">8</td>
                    </tr>
                    <tr>
                        <td class="sol-metin text-left border-b border-gray-200">Isıtma</td>
                        <td class="sag-metin text-right border-b border-gray-200">Sobalı</td>
                    </tr>
                    <tr>
                        <td class="sol-metin text-left border-b border-gray-200">Balkon</td>
                        <td class="sag-metin text-right border-b border-gray-200">Var</td>
                    </tr>
                    <tr>
                        <td class="sol-metin text-left border-b border-gray-200">Asansör</td>
                        <td class="sag-metin text-right border-b border-gray-200">Var</td>
                    </tr>
                    <tr>
                        <td class="sol-metin text-left border-b border-gray-200">Otopark</td>
                        <td class="sag-metin text-right border-b border-gray-200">Açık Otopark</td>
                    </tr>
                    <tr>
                        <td class="sol-metin text-left border-b border-gray-200">Eşyalı</td>
                        <td class="sag-metin text-right border-b border-gray-200">Evet</td>
                    </tr>
                    <tr>
                        <td class="sol-metin text-left border-b border-gray-200">Aidat</td>
                        <td class="sag-metin text-right border-b border-gray-200">500 TL</td>
                    </tr>
                    <tr>
                        <td class="sol-metin text-left border-b border-gray-200">Başlık</td>
                        <td class="sag-metin text-right border-b border-gray-200">500 TL</td>
                    </tr>
                    <tr>
                        <td class="sol-metin text-left">Kimden</td>
                        <td class="sag-metin text-right">Çelik Emlak</td>
                    </tr>

                </thead>
            </table>

        </div>
        <div class="kutu4">
            <div class="uye-adi text-xl pt-4 pl-4">MEHMET REŞİT GÜRHAN</div>
            <div class="hesap-acma-tarihi text-xs pt-1 pl-4">Hesap Açma Tarihi: 12.05.2024</div>
            <div class="uye-tel tracking-wider pt-3 pl-4"><a href="#"><i class="fa-solid fa-phone"> +90 506 057
                        4014</i></a></div>
            <div class="uye-wp-tel tracking-wider pt-2 pl-4"><a href="#" target="_blank"><i
                        class="fa-brands fa-whatsapp"> +90 506 057 4014</i></a></div>
            <div class="profili-gor w-32 h-6 rounded-full bg-blue-500 text-white flex justify-center ml-16 mt-2">Profili
                Gör
            </div>
        </div>
        <div class="kutu5">
            <center>İLAN REKLAM İÇERİK ALANIDIR</center>
        </div>
        <div class="kutu6">
            <b>İlan Açıklama</b>
        </div>
        <div class="kutu7 p-2">
            <p>
                AUDI A5<br />
                EMSALSİZ TEMİZLİKTEDİR ALICISINA ŞİMDİDEN HAYIRLI OLSUN<br />
                ⛽️ YAKIT: DİZEL ✅<br />
                ✅AKÜ SIFIR<br />
                ✅ALT TAKIM SALANCAKLAR SIFIR<br />
                ✅BASKI BALATA SIFIR<br />
                ✅4 LASTİK KIŞLIK SIFIR<br />
                ✅KLİMA AKTİF<br />
                ✅2 CAM OTOMATİK<br />
                ✅ABS<br />
                ✅KIŞLIK BAKIMI YENİ YAPILDI
            </p>
        </div>
        <div class="kutu8">
            <center>İLAN REKLAM İÇERİK ALANIDIR</center>
        </div>
    </div>
    <myFooter />
</template>

<style scoped>
.container {
    display: grid;
    max-width: 71rem;
    height: auto;
    grid-template-rows: auto 1fr 1fr 1fr auto 18rem;
    grid-template-columns: 1fr 1fr 1fr 16.5rem;
    justify-content: center;
    margin: 0 auto;
    gap: 0.8rem;
}

.kutu1 {
    grid-row: 1;
    grid-column: 1/5;
    height: 3.8rem;
    font-size: 1.8rem;
    font-weight: 500;
    padding: 0.5rem 0rem;
}

.kutu2 {
    grid-row: 2/5;
    grid-column: 1/3;
    box-shadow: rgba(0, 0, 0, 0.25) 0px 14px 28px, rgba(0, 0, 0, 0.22) 0px 10px 10px;
}

/* KUTU2 içerisinde olan ana resmin altında resimler için grid kodları aşağıda yazılmıştır */
.mini-resimler {
    display: flex;
    float: left;
    max-width: 5.2rem;
    margin: 0.3rem 0.3rem 0.4rem 0.4rem;
}

.kutu3 {
    grid-row: 2/5;
    grid-column: 3;
    padding: 0.5rem 1rem;
    font-size: 14px;
    box-shadow: rgba(0, 0, 0, 0.25) 0px 14px 28px, rgba(0, 0, 0, 0.22) 0px 10px 10px;
}

/* KUTU3 ile alakalı detay verilen metinlerin kodları aşağıdadır */
.ilan_fiyat {
    font-size: 1.5rem;
    font-weight: 500;
    color: #059;
}

.ilan_konum {
    font-size: 1rem;
    color: #059;
}

.sol-metin {
    color: #059;
    font-weight: 500;
    padding-top: 0.4rem;
}

.kutu4 {
    grid-row: 2/3;
    grid-column: 4;
    box-shadow: rgba(0, 0, 0, 0.25) 0px 14px 28px, rgba(0, 0, 0, 0.22) 0px 10px 10px;
}

.kutu5 {
    grid-row: 3/5;
    grid-column: 4;
    box-shadow: rgba(0, 0, 0, 0.25) 0px 14px 28px, rgba(0, 0, 0, 0.22) 0px 10px 10px;
}

.kutu6 {
    grid-row: 5;
    grid-column: 1/5;
    margin-top: 0.5rem;
}

.kutu7 {
    grid-row: 6;
    grid-column: 1/4;
    box-shadow: rgba(0, 0, 0, 0.25) 0px 14px 28px, rgba(0, 0, 0, 0.22) 0px 10px 10px;
}

.kutu8 {
    grid-row: 6;
    grid-column: 4/5;
    box-shadow: rgba(0, 0, 0, 0.25) 0px 14px 28px, rgba(0, 0, 0, 0.22) 0px 10px 10px;
}

@media all and (max-width:768px) {
    .container {
        max-width: 100%;
        height: auto;
        grid-template-rows: auto auto auto auto auto auto;
        grid-template-columns: 1fr;
        gap: 0rem;
    }

    .kutu1 {
        /* başlık burdadır */
        grid-row: 1;
        grid-column: 1;
        height: 2.5rem;
        justify-content: center;
        text-align: center;
        font-size: 1rem;
        font-weight: 400;
        align-items: center;
        justify-content: center;
    }

    .kutu2 {
        /* ana resim burdadır */
        grid-row: 2;
        grid-column: 1;
        box-shadow: none;
        /* margin:0rem 0.5rem; */
    }

    .kutu4 {
        /* müşteri adı ve kayıt tarihi */
        grid-row: 3;
        grid-column: 1;
        text-align: center;
        padding-bottom: 1rem;
        box-shadow: none;
    }

    .uye-adi {
        /* üye adının olduğu stil kodlarıdır */
        padding-top: 0.5rem;
        font-size: 1rem;
        font-weight: 500;
    }

    .hesap-acma-tarihi {
        padding-top: 0rem;
    }

    .mobil-degisken-icerik {
        /*ilan açıklama konumu başlıkları burdadır */
        grid-row: 4;
        grid-column: 1;
        display: inline-grid;
        border-bottom: 0.1rem solid #475569;
        grid-template-columns: repeat(3, 1fr);
        grid-template-rows: repeat(1, auto);
    }

    .kutu3 {
        /* burada ilan detayları bulunur */
        grid-row: 6;
        grid-column: 1;
        margin-bottom: 2.5rem;
        padding: 0.3rem;
    }

    .sag-metin {
        padding-right: 0.5rem;
    }

    /* .mobilde-gorunecek-fiyat{
        display: unset;
    } */
    /* 
    .kutu3{
        background-color: #059;
    } */

    .ilan_fiyat,
    .ilan_konum,
    .mini-resimler,
    .kutu5,
    .kutu6,
    .kutu7,
    .kutu8,
    .uye-tel,
    .uye-wp-tel,
    .profili-gor {
        display: none;
    }

}
</style>

<script setup>
const vitrinResim = [
    { id: 1, image: 'buyuk-resim.jpg', description: 'Açıklama 1' },
    { id: 2, image: 'c.jpg', description: 'Açıklama 2' },
    { id: 3, image: 'c.jpg', description: 'Açıklama 3' },
    { id: 4, image: 'c.jpg', description: 'Açıklama 4' },
    { id: 5, image: 'c.jpg', description: 'Açıklama 5' },
    { id: 6, image: 'c.jpg', description: 'Açıklama 6' },
    { id: 7, image: 'c.jpg', description: 'Açıklama 7' },
    { id: 8, image: 'c.jpg', description: 'Açıklama 8' },
    { id: 9, image: 'c.jpg', description: 'Açıklama 9' },
    { id: 10, image: 'c.jpg', description: 'Açıklama 10' },
    { id: 11, image: 'c.jpg', description: 'Açıklama 11' },
    { id: 12, image: 'c.jpg', description: 'Açıklama 12' },
    { id: 13, image: 'c.jpg', description: 'Açıklama 13' }
];
</script>
<script>
import myFooter from '~/pages/myFooter.vue'; // footer bileşenini içeri aktar
export default {
    components: {
        myFooter // Footer bileşenini kullanılabilir hale getir
    }
}
</script>