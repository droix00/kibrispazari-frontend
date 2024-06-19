<template>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css"
        integrity="shfiyat12-DTOQO9RWCH3ppGqcWaEbosBIZOC6xxalwEsw9c2QQeAIftl+Vegovlnee1c9QX4TctnWMn13TZye+giMm8e2LwA=="
        crossorigin="anonymous" referrerpolicy="no-referrer" />
    <div class="content">
        <div class="content__menu">
            <h2 class="content__menu-title">Alt Kategoriler</h2>
            <ul class="content__menu-list">
                <li class="content__menu-item">
                    <div v-for="item in solMenu" :key="index">
                        <span class="m-auto"><i :class="item.icon"></i></span>
                        <a :href="item.to" class="hover:bg-blue-50"> {{ item.title }}</a>
                    </div>
                </li>
                <br />
                <h2 class="content__menu-title">Konum</h2>
                <USelectMenu v-model="selected_cities" :options="cities" />
            </ul>
        </div>
        <div class="content__vitrine">
            <h2 class="content__vitrine-title" id="metinAlanı">Emlak Vitrini {{ selected_cities == 'Seçiniz' ? '' : '|' +
                        selected_cities }} </h2>
            <div class="basliklar ml-5 my-1 py-1 flex flex-row bg-zinc-200 text-black">
                <div class="gridim">
                    <div class="bos border-r border-gray-300"></div>
                    <div class="ilan_basligi border-r border-gray-300">İlan Başlığı</div>
                    <div class="metrekare border-r border-gray-300">m² (Brüt)</div>
                    <div class="oda_sayisi border-r border-gray-300">Oda Sayısı</div>
                    <div class="fiyat border-r border-gray-300">Fiyat</div>
                    <div class="ilan_tarihi border-r border-gray-300">İlan Tarihi</div>
                    <div class="konum border-r border-gray-300">Konum</div>
                </div>
            </div>
            <div class="content__vitrine-grid">
                <!-- Buraya dinamik olarak içerik ekleyebilirsiniz -->
                <div v-for="item in vitrineItem.slice(0, 35)" :key="item.id"
                    :class="[getBackgroundColor(item.id), 'content__vitrine-item']">
                    <a :href="'/' + item.link" class="block w-full hover:bg-blue-50">
                        <div class="denemem text-sm flex flex-row">
                            <img :src="item.image" alt="Resim">
                            <div class="ilan_basligi border-r border-gray-300 pl-1">{{ item.title }}</div>
                            <div class="metrekare border-r border-white-300">{{ item.area }}</div>
                            <div class="oda_sayisi border-r border-gray-300">{{ item.roomCount }}</div>
                            <div class="fiyat border-r border-gray-300 text-red-800">{{ item.price }}</div>
                            <div class="ilan_tarihi border-r border-gray-300">{{ item.listingDate }}</div>
                            <div class="konum border-r border-black-300"><i
                                    class="lokasyon fa-solid fa-location-dot"></i>
                                {{ item.location }}</div>
                        </div>
                    </a>
                </div>
            </div>
        </div>
    </div>
    <myFooter />
</template>
<script>
const cities = ['Seçiniz', 'Lefkoşa', 'Girne', 'Lefke', 'Güzelyurt'] //sol layout'taki selectbox için script kodları
const selected_cities = ref(cities[0]);

import myFooter from '~/pages/myFooter.vue'; // Header bileşenini içeri aktar
export default {
    components: {
        myFooter // Footer bileşenini kullanılabilir hale getir
    }
}
</script>

<script setup>
const solMenu = [{
    icon: 'fa-solid fa-house-flag',
    title: 'Emlak',
    to: 'deneme'
}, {
    icon: 'fa-solid fa-house-user ml-4 my-2',
    title: 'Kiralık Daire',
    to: 'deneme'
}, {
    icon: 'fa-solid fa-house-circle-check ml-4 my-2',
    title: 'Satılık Daire',
    to: 'deneme'
}, {
    icon: 'fa-solid fa-house-chimney ml-4 my-2',
    title: 'Villa',
    to: 'deneme'
}, {
    icon: 'fa-solid fa-shop ml-4 my-2',
    title: 'İş Yeri',
    to: 'deneme'
}, {
    icon: 'fa-solid fa-map-marked-alt ml-4 my-2',
    title: 'Arazi',
    to: ''
}]

const getBackgroundColor = (id) => {
    return id % 2 === 1 ? 'bg-wheat' : 'bg-zinc-100';
}
const vitrineItem = [
    { id: 1, image: 'a.jpg', description: 'Açıklama 1', link: 'ilan', price: '12.000.000 TL', title: "BEYLİKDÜZÜ VESADAN METROBÜS DURAĞINA KOMŞU 2+1 SATILIK ARAKAT!", area: '200', roomCount: '3+1', listingDate: '06 Haziran 2024', location: 'Lefkoşa Göçmenköy' },
    { id: 2, image: 'b.jpg', description: 'Açıklama 1', link: 'ilan', price: '12.000.000 TL', title: "DELİKLİTAŞ CADDESİ'NDE SATILIK 3+1 KOMBİLİ GENİŞ VE FERAH DAİRE GONCA EMLAK", area: '200', roomCount: '3+1', listingDate: '06 Haziran 2024', location: 'Lefkoşa Göçmenköy' },
    { id: 3, image: 'c.jpg', description: 'Açıklama 1', link: 'ilan', price: '12.000.000 TL', title: "ETLİK ŞEHİR HASTANESİ & ANTARES AVM YAKINI İSKANLI 3+1 MASRAFSIZ STAR LİFE GAYRİMENKUL", area: '200', roomCount: '3+1', listingDate: '06 Haziran 2024', location: 'Lefkoşa Göçmenköy' },
    { id: 4, image: 'a.jpg', description: 'Açıklama 1', link: 'ilan', price: '12.000.000 TL', title: "SONSUZDAN BÖLGENİN ŞIK GENİŞ 5+2 KELEPİR DUBLEKSİ", area: '200', roomCount: '3+1', listingDate: '06 Haziran 2024', location: 'Lefkoşa Göçmenköy' },
    { id: 5, image: 'b.jpg', description: 'Açıklama 1', link: 'ilan', price: '12.000.000 TL', title: "BOZARMUT'TA ŞOK ŞOK ÇOK ACİL YARI FİYATA 280 m2 ARSA VE EV KAÇAR IMM ZEYTİNAĞACI HOLDİNG", area: '200', roomCount: '3+1', listingDate: '06 Haziran 2024', location: 'Lefkoşa Göçmenköy' },
    { id: 6, image: 'c.jpg', description: 'Açıklama 1', link: 'ilan', price: '12.000.000 TL', title: "DELİKLİTAŞ CADDESİ'NDE SATILIK 3+1 KOMBİLİ GENİŞ VE FERAH DAİRE GONCA EMLAK", area: '200', roomCount: '3+1', listingDate: '06 Haziran 2024', location: 'Lefkoşa Göçmenköy' },
    { id: 7, image: 'a.jpg', description: 'Açıklama 1', link: 'ilan', price: '12.000.000 TL', title: "ETLİK ŞEHİR HASTANESİ & ANTARES AVM YAKINI İSKANLI 3+1 MASRAFSIZ STAR LİFE GAYRİMENKUL", area: '200', roomCount: '3+1', listingDate: '06 Haziran 2024', location: 'Lefkoşa Göçmenköy' },
    { id: 8, image: 'b.jpg', description: 'Açıklama 1', link: 'ilan', price: '12.000.000 TL', title: "BEYLİKDÜZÜ VESADAN METROBÜS DURAĞINA KOMŞU 2+1 SATILIK ARAKAT!", area: '200', roomCount: '3+1', listingDate: '06 Haziran 2024', location: 'Lefkoşa Göçmenköy' },
    { id: 9, image: 'c.jpg', description: 'Açıklama 1', link: 'ilan', price: '12.000.000 TL', title: "SONSUZDAN BÖLGENİN ŞIK GENİŞ 5+2 KELEPİR DUBLEKSİ", area: '200', roomCount: '3+1', listingDate: '06 Haziran 2024', location: 'Lefkoşa Göçmenköy' },
    { id: 10, image: 'c.jpg', description: 'Açıklama 10', link: 'ilan', price: 100 },
    { id: 11, image: 'c.jpg', description: 'Açıklama 11', link: 'ilan', price: 200 },
    { id: 12, image: 'c.jpg', description: 'Açıklama 12', link: 'ilan', price: 300 },
    { id: 13, image: 'c.jpg', description: 'Açıklama 13', link: 'ilan', price: 400 },
    { id: 14, image: 'c.jpg', description: 'Açıklama 14', link: 'ilan', price: 500 },
    { id: 15, image: 'c.jpg', description: 'Açıklama 15', link: 'ilan', price: 600 },
    { id: 16, image: 'c.jpg', description: 'Açıklama 16', link: 'ilan', price: 800 },
    { id: 17, image: 'c.jpg', description: 'Açıklama 17', link: 'ilan', price: 400 },
    { id: 18, image: 'c.jpg', description: 'Açıklama 18', link: 'ilan', price: 300 },
    { id: 19, image: 'c.jpg', description: 'Açıklama 19', link: 'ilan', price: 300 },
]
</script>

<style scoped>
.content {
    /*Content alanı */
    display: flex;
    margin: 0rem 12.2rem 2rem 12.8rem;
}

.content__menu {
    /*contentteki sol menü kategoriler ve alt başlıkları */
    flex: 1;
    padding: 1rem 1rem 1rem 0rem;
    /* margin-left:12rem; */
}

.content__menu-title {
    /*Kategoriler */
    margin-bottom: 1rem;
    font-weight: bold;
}

.content__menu-list {
    /*alt kategoriler */
    list-style-type: none;
}

.content__menu-item {
    /* her alt kategori için bottom ayarlandı */
    margin-bottom: 0.5rem;
}

.content__menu-item i {
    width: 1.3rem;
}

.content__menu-link {
    /* kategorilerdeki link ayarları */
    color: #333;
    text-decoration: none;
}

.content__menu-link:hover {
    /* kategorilerdeki link ayarlarının hoveri ayarlandı */
    color: #558;
}

.content__vitrine {
    /* anasayfa vitrini ürünleri alanı */
    flex:7;
    padding: 1rem 0rem;
}

.content__vitrine-title {
    margin-bottom: 1rem;
    /*anasayfa başlık yazısı ayarı */
    font-weight: bold;
    margin-left: 1.2rem;
}

.gridim {
    display: grid;
    grid-template-columns: repeat(23,1fr);
    grid-template-rows: 1fr;
}

.bos,.ilan_basligi,.metrekare,.oda_sayisi,.fiyat,.ilan_tarihi,.konum {
    grid-row: 1 / 2; /* satır */
    text-align: center;
    justify-content: center;
    align-items: center;
}
.bos{
    grid-column: 1/ 5; /* sütun */
    background-color: red;
}
.ilan_basligi {
    grid-column: 5/ (14,5); /* sütun */
    background-color: green;
}

.metrekare { grid-column: 15/ 17; /* sütun */
    background-color: blue;
}

.oda_sayisi { grid-column: 17/ 19; /* sütun */
    background-color: gold;
}

.fiyat { grid-column: 19/ 21; /* sütun */
    background-color: rgb(186, 41, 174);
}

.ilan_tarihi { grid-column: 21/ 23; /* sütun */
    background-color: aqua;

}
.konum { grid-column: 23/ 24; /* sütun */

}
.lokasyon {
    display: none;
}

.content__vitrine-grid {
    /* anasayfa vitrini gridi */
    display: grid;
    grid-template-columns: repeat(1, 1fr);
    gap: 0.2rem;
    margin-left: 1.2rem;
    border-bottom: 1px solid #ccc;
}

.content__vitrine-item {
    /* anasayfa vitrinindeki her ürünün ayarı*/
    padding: 0rem;
    width: 100%;
}

.content__vitrine-item img {
    /* anasayfa vitrinindeki her ürünün resim ayarı */
    width: 11.1rem;
    height: 9rem;
    background-size: cover;
    flex-wrap: wrap;
    /* height: auto; */
}

@media all and (max-width:768px) {
    .content {
        /*Content alanı */
        margin: 0rem 0rem 0rem 0rem;
        flex-direction: column;
        /*mobil için dikey düzen ayarı*/
    }

    .content__vitrine-grid {
        /* anasayfa vitrini gridi */
        margin-left: 0;
        margin-right: 0;
        padding: 0.2rem;
    }

    .content__vitrine-title {
        margin-left: 0.2rem;
    }

    .content__vitrine-item {
        width: 100%;
        display: flex;
        flex: 10;
        flex-wrap: wrap;
    }

    .denemem {
        display: grid;
        grid-template-columns: auto 1fr;
        grid-template-rows: auto auto auto;
        /* Resim için otomatik genişlik, geri kalan alan 1 fraksiyonlu */
    }


    .content__vitrine-item img {
        width: 8rem;
        height: 7.5rem;
        grid-row: 1/ span 3;
        /* İlk iki satırı kaplar */
        grid-column: 1;
        /* Resim birinci sütunda */
    }

    .ilan_basligi {
        display: block;
        max-height: 4rem;
        margin: 1rem 0.2rem 0rem 0rem;
        border-right: none;
        flex-direction: column;
        grid-row: 1 / span 3;
        /* bir iki ve üçüncü satırları kaplar*/
        grid-column: 2/ span 3;
        /* İkinci sütunu kaplar */
        overflow: hidden;
        /* Taşan kısmı gizle */
        text-overflow: ellipsis;
        /* Taşan kısmı ... olarak göster */
        white-space: normal;
        line-height: 1.25em;
    }

    .fiyat {
        border-right: none;
        width: 10rem;
        letter-spacing: 0.2px;
        justify-content: flex-end;
        padding-right: 0.5rem;
        margin-bottom: 1rem;
        color: #32628D;
        font-weight: 500;
        grid-row: 3/ span 4;
        /* üçüncü satırda */
        grid-column: 3;
        /* üçüncü sütunda */
    }

    .lokasyon {
        display: inline;
        margin-right: 0.2rem;
    }

    .konum {
        border-right: none;
        margin-bottom: 1rem;
        font-size: 14px;
        width: 12rem;
        justify-content: flex-start;
        padding-left: 0.4rem;
        grid-row: 3/ span 4;
        /* Üçüncü satırda */
        grid-column: 2;
        /* İkinci sütunda */
    }

    /* DENEM BİTİŞ */

    .basliklar,
    .content__menu,
    .metrekare,
    .oda_sayisi,
    .ilan_tarihi {
        display: none;
    }
}
</style>