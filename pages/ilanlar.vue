<template>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css"
        integrity="shfiyat12-DTOQO9RWCH3ppGqcWaEA1BIZOC6xxalwEsw9c2QQeAIftl+Vegovlnee1c9QX4TctnWMn13TZye+giMm8e2LwA=="
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
            <h2 class="content__vitrine-title" id="metinAlanı">Emlak Vitrini {{ selected_cities == 'Seçiniz' ? '' : '|'
                +
                selected_cities }} </h2>
            <div class="basliklar ml-5 my-1 py-1 flex flex-row bg-zinc-200 text-black">
                <div class="a1 border-r border-gray-300"></div>
                <div class="title border-r border-gray-300">İlan Başlığı</div>
                <div class="metrekare border-r border-gray-300">m² (Brüt)</div>
                <div class="oda_sayisi border-r border-gray-300">Oda Sayısı</div>
                <div class="fiyat border-r border-gray-300">Fiyat</div>
                <div class="ilan_bilgileri_tarihi border-r border-gray-300">İlan Tarihi</div>
                <div class="ilan_bilgileri_konum border-r border-gray-300">Konum</div>
            </div>
            <div class="content__vitrine-grid">
                <!-- Buraya dinamik olarak içerik ekleyebilirsiniz -->
                <div v-for="item in vitrineItem.slice(0, 35)" :key="item.id"
                    :class="[getBackgroundColor(item.id), 'content__vitrine-item']">
                    <a :href="'/' + item.link" class="block w-full hover:bg-blue-50">
                        <div class="denemem text-sm flex flex-row">
                            <div class="resim">
                                <img :src="item.image" alt="Resim">
                            </div>
                            <div class="title border-r border-gray-300 pl-1">{{ item.title }}</div>
                            <div class="metrekare border-r border-white-300">{{ item.area }}</div>
                            <div class="oda_sayisi border-r border-gray-300">{{ item.roomCount }}</div>
                            <div class="fiyat border-r border-gray-300 text-red-800">{{ item.price }}</div>
                            <div class="ilan_bilgileri_tarihi border-r border-gray-300">{{ item.listingDate }}</div>
                            <div class="ilan_bilgileri_konum border-r border-black-300"><i
                                    class="lokasyon fa-solid fa-location-dot"></i> {{ item.location }}</div>
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
    { id: 1, image: 'a.jpg', description: 'Açıklama 1', link: 'ilan_bilgileri', price: '999.000.000 TL', title: "BEYLİKDÜZÜ VESADAN METROBÜS DURAĞINA KOMŞU 2+1 SATILIK ARAKAT!", area: '200', roomCount: '3+1', listingDate: '06 Haziran 2024', location: 'Lefkoşa Göçmenköy' },
    { id: 2, image: 'b.jpg', description: 'Açıklama 1', link: 'ilan_bilgileri', price: '12.000.000 TL', title: "DELİKLİTAŞ CADDESİ'NDE SATILIK 3+1 KOMBİLİ GENİŞ VE FERAH DAİRE GONCA EMLAK", area: '200', roomCount: '3+1', listingDate: '06 Haziran 2024', location: 'Lefkoşa Metehan' },
    { id: 3, image: 'c.jpg', description: 'Açıklama 1', link: 'ilan_bilgileri', price: '12.000.000 TL', title: "ETLİK ŞEHİR HASTANESİ & ANTARES AVM YAKINI İSKANLI 3+1 MASRAFSIZ STAR LİFE GAYRİMENKUL", area: '200', roomCount: '3+1', listingDate: '06 Haziran 2024', location: 'Lefkoşa ' },
    { id: 4, image: 'a.jpg', description: 'Açıklama 1', link: 'ilan_bilgileri', price: '12.000.000 TL', title: "SONSUZDAN BÖLGENİN ŞIK GENİŞ 5+2 KELEPİR DUBLEKSİ", area: '200', roomCount: '3+1', listingDate: '06 Haziran 2024', location: 'Lefkoşa Göçmenköy' },
    { id: 5, image: 'b.jpg', description: 'Açıklama 1', link: 'ilan_bilgileri', price: '12.000.000 TL', title: "BOZARMUT'TA ŞOK ŞOK ÇOK ACİL YARI FİYATA 280 m2 ARSA VE EV KAÇAR IMM ZEYTİNAĞACI HOLDİNG", area: '200', roomCount: '3+1', listingDate: '06 Haziran 2024', location: 'Lefkoşa Göçmenköy' },
    { id: 6, image: 'c.jpg', description: 'Açıklama 1', link: 'ilan_bilgileri', price: '12.000.000 TL', title: "DELİKLİTAŞ CADDESİ'NDE SATILIK 3+1 KOMBİLİ GENİŞ VE FERAH DAİRE GONCA EMLAK", area: '200', roomCount: '3+1', listingDate: '06 Haziran 2024', location: 'Lefkoşa Göçmenköy' },
    { id: 7, image: 'a.jpg', description: 'Açıklama 1', link: 'ilan_bilgileri', price: '12.000.000 TL', title: "ETLİK ŞEHİR HASTANESİ & ANTARES AVM YAKINI İSKANLI 3+1 MASRAFSIZ STAR LİFE GAYRİMENKUL", area: '200', roomCount: '3+1', listingDate: '06 Haziran 2024', location: 'Lefkoşa Göçmenköy' },
    { id: 8, image: 'b.jpg', description: 'Açıklama 1', link: 'ilan_bilgileri', price: '12.000.000 TL', title: "BEYLİKDÜZÜ VESADAN METROBÜS DURAĞINA KOMŞU 2+1 SATILIK ARAKAT!", area: '200', roomCount: '3+1', listingDate: '06 Haziran 2024', location: 'Lefkoşa Göçmenköy' },
    { id: 9, image: 'c.jpg', description: 'Açıklama 1', link: 'ilan_bilgileri', price: '12.000.000 TL', title: "SONSUZDAN BÖLGENİN ŞIK GENİŞ 5+2 KELEPİR DUBLEKSİ", area: '200', roomCount: '3+1', listingDate: '06 Haziran 2024', location: 'Lefkoşa Göçmenköy' },
    { id: 10, image: 'c.jpg', description: 'Açıklama 10', link: 'ilan_bilgileri', price: 100 },
    { id: 11, image: 'c.jpg', description: 'Açıklama 11', link: 'ilan_bilgileri', price: 200 },
    { id: 12, image: 'c.jpg', description: 'Açıklama 12', link: 'ilan_bilgileri', price: 300 },
    { id: 13, image: 'c.jpg', description: 'Açıklama 13', link: 'ilan_bilgileri', price: 400 },
    { id: 14, image: 'c.jpg', description: 'Açıklama 14', link: 'ilan_bilgileri', price: 500 },
    { id: 15, image: 'c.jpg', description: 'Açıklama 15', link: 'ilan_bilgileri', price: 600 },
    { id: 16, image: 'c.jpg', description: 'Açıklama 16', link: 'ilan_bilgileri', price: 800 },
    { id: 17, image: 'c.jpg', description: 'Açıklama 17', link: 'ilan_bilgileri', price: 400 },
    { id: 18, image: 'c.jpg', description: 'Açıklama 18', link: 'ilan_bilgileri', price: 300 },
    { id: 19, image: 'c.jpg', description: 'Açıklama 19', link: 'ilan_bilgileri', price: 300 },
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
    color: #fa6558;
}

.content__vitrine {
    /* anasayfa vitrini ürünleri alanı */
    padding: 1rem 0rem;
}

.content__vitrine-title {
    margin-bottom: 1rem;
    /*anasayfa başlık yazısı ayarı */
    font-weight: bold;
    margin-left: 1.2rem;
}

.a1 {
    width: 11.05rem;
    text-align: center;
}

.title {
    width: 23.1rem;
    display: flex;
    justify-content: center;
    align-items: center;
}

.metrekare {
    width: 4.5rem;
    text-align: center;
    display: flex;
    justify-content: center;
    align-items: center;
}

.oda_sayisi {
    width: 5rem;
    text-align: center;
    display: flex;
    justify-content: center;
    align-items: center;
}

.fiyat {
    width: 5.5rem;
    text-align: center;
    display: flex;
    justify-content: center;
    align-items: center;
}

.ilan_bilgileri_tarihi {
    width: 5rem;
    text-align: center;
    display: flex;
    justify-content: center;
    align-items: center;
}

.ilan_bilgileri_konum {
    width: 5.3rem;
    text-align: center;
    display: flex;
    justify-content: center;
    align-items: center;
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

@media all and (max-width:932px) {
    .content {
        /*Content alanı */
        margin: 0rem 0rem 0rem 0rem;
        flex-direction: column;
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

    .denemem {
        display: grid;
        grid-template-columns: 3.3rem 1fr 1fr 1fr 1fr 1fr;
        grid-template-rows: 1fr 1fr 1fr;
        /* Resim için otomatik genişlik, geri kalan alan 1 fraksiyonlu */
    }


    .resim {
        grid-row: 1/ span 3;
        /* İlk iki satırı kaplar */
        grid-column: 1/span 2;
        /* Resim birinci sütunda */
    }

    .content__vitrine-item img {
        height: auto;
    }

    .title {
        width: auto;
        border-right: none;
        margin: 0rem 0.2rem 0.2rem 0.2rem;
        grid-row: 1 / 3;
        /* bir iki ve üçüncü satırları kaplar*/
        grid-column: 3/ 8;
        /* İkinci sütunu kaplar */
        overflow: hidden;
        /* Taşan kısmı gizle */
        text-overflow: ellipsis;
        /* Taşan kısmı ... olarak göster */
        white-space: wrap;
        line-height: 1.25em;
        justify-content: flex-start;
    }

    .fiyat {
        width: auto;
        border-right: none;
        grid-row: 3/span 4;
        /* üçüncü satırda */
        grid-column: 5/ 7;
        /* üçüncü sütunda */
        justify-content: flex-end;
        padding-right: 0.4rem;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
        font-weight: 500;

    }

    .lokasyon {
        display: inline;
        margin: 0rem 0.2rem 0rem 0.5rem;
    }

    .ilan_bilgileri_konum {
        width: 8rem;
        font-size: 0.75rem;
        opacity: 0.8;
        border-right: none;
        justify-content: flex-start;
        grid-row: 3/span 4;
        /* Üçüncü satırda */
        grid-column: 3/ 5;
        /* İkinci sütunda */
    }


    /* DENEM BİTİŞ */

    .basliklar,
    .content__menu,
    .metrekare,
    .oda_sayisi,
    .ilan_bilgileri_tarihi {
        display: none;
    }
}
</style>