<template>
    <HeaderComponent />
    <div class="content">
        <div class="ust_baslik">
            YATIRIM AMAÇLI YÜKSEK KİRA GETİRİLİ TEMİZ DAİRE
            <hr />
        </div>
        <div class="ilan_content">
            <div class="ilan_resim_alani">
                <div v-for="item in vitrineItem.slice(0, 1)" :key="item.id" class="ana_resim">
                    <img :src="item.image" alt="Resim">
                </div>
                <div v-for="item in vitrineItem.slice(1, 13)" :key="item.id" class="alt_resim">
                    <img :src="item.image" alt="Resim">
                </div>
            </div>
            <router-link to="/sikca_sorulan_sorular" class="content__menu-link"></router-link>
            <div class="degisen_icerik text-center">
                <router-link to="/ilan_bilgileri"><div class="baslik1 bg-slate-700 text-white ml-2 p-2">İlan Bilgileri</div></router-link>
                <router-link to="/ilan_aciklama"><div class="baslik2 border border-slate-300 ml-2 p-2">Açıklama</div></router-link>
                <router-link to="/ilan_konumu"><div class="baslik2 border border-slate-300 ml-2 mr-2 p-2">Konumu</div></router-link>
            </div>
            <div class="ilan_bilgileri">
                <div class="ilan_fiyat">3.600.000 TL</div>
                <div class="ilan_adres">Kıbrıs / Lefkoşa / Gönyeli</div> 
                <router-view class="routerimiz"></router-view>
                
            </div>
            <div class="ilan_iletisim"> 
                <div class="ilan_sahibi">
                    <div class="uye_adi">MEHMET REŞİT GÜRHAN</div>
                    <div class="uye_kayit_tarihi">Hesap Açma Tarihi: 12.05.2024</div>
                    <div class="uye_tel"><a href="tel:+905060574014"><i class="fa-solid fa-phone">+90 506 057
                                4014</i></a></div>
                    <div class="uye_wp_tel"><a href="wa.me/+905060574014" target="_blank"><i
                                class="fa-brands fa-whatsapp"> +90 506 057 4014</i></a></div>
                </div>
                <div class="ilan_reklam">İLAN REKLAM ALANIDIR</div>
            </div>
        </div>

        <div class="ilan_aciklama_title">İlan Açıklama</div>
        <div class="alt_bolum">
            <div class="ilan_aciklama">
                AUDI A5<br />
                EMSALSİZ TEMİZLİKTEDİR ALICISINA ŞİMDİDEN HAYIRLI OLSUN
                <br />⛽️ YAKIT: DİZEL ✅
                <br />✅AKÜ SIFIR
                <br />✅ALT TAKIM SALANCAKLAR SIFIR
                <br />✅BASKI BALATA SIFIR
                <br />✅4 LASTİK KIŞLIK SIFIR
                <br />✅KLİMA AKTİF
                <br />✅2 CAM OTOMATİK
                <br />✅ABS
                <br />✅KIŞLIK BAKIMI YENİ YAPILDI
            </div>
            <div class="ilan_aciklama_reklam">İLAN AÇIKLAMA REKLAM</div>
        </div>
    </div>
    <div class="kisiyi_ara">
        <div class="cepten_ara">Hemen Ara</div>
        <div class="wp_ara">Whatsapp</div>
    </div>
    <myFooter />
    <br/><br/><br/>
</template>

 
<script>
import HeaderComponent from '~/layouts/default.vue'; // default.vue dosyasını import edip header bileşenini çağırdık
import myFooter from '~/pages/myFooter.vue'; // footer bileşenini içeri aktar


export default {
    components: {
        HeaderComponent, myFooter // Footer bileşenini kullanılabilir hale getir
    }
}
</script>

<script setup>
</script>

<style scoped>
.content {
    /*Content alanı */
    display: block;
}

.ust_baslik {
    flex: 1;
    font-size: 1.8rem;
    font-weight: 500;
    padding: 0.8rem 12.3rem;
}

.ilan_content {
    display: flex;
}

.ilan_resim_alani {
    max-width: 35rem;
    margin-left: 12.6rem;
    box-shadow: rgba(0, 0, 0, 0.25) 0px 14px 28px, rgba(0, 0, 0, 0.22) 0px 10px 10px;
}

.ana_resim {
    max-width: 35rem;
    margin-bottom: 0.5rem;
}

.alt_resim {
    float: left;
    max-width: 5.2rem;
    margin: 0rem 0.4rem 0.4rem 0.23rem;
}

.ilan_bilgileri {
    padding: 0.5rem 1rem 0rem 1rem;
    box-shadow: rgba(0, 0, 0, 0.25) 0px 14px 28px, rgba(0, 0, 0, 0.22) 0px 10px 10px;
    margin-left: 1rem;
    padding-left: 1.7rem;
    padding-right: 1.7rem;
}

.ilan_fiyat {
    font-size: 1.5rem;
    font-weight: 500;
    color: #059;
}

.ilan_adres {
    font-size: 1rem;
    color: #059;
}

.ad-property ul {
    border-spacing: 0rem 0.65rem;
}

.ad-property ul li {
    display: table-row;
    font-size: 14px;
    color: #059;
    font-weight: 500;
}

.ad-property ul li span {
    display: table-cell;
    color: black;
    font-weight: normal;
    padding-left: 3rem;
}

.ilan_iletisim {
    display: block;
    margin-left: 1rem;
    max-width: 52rem;
    padding-right: 2rem;
    width: 18.5rem;
}

.ilan_sahibi {
    padding: 1rem;
    box-shadow: rgba(0, 0, 0, 0.25) 0px 14px 28px, rgba(0, 0, 0, 0.22) 0px 10px 10px;
}

.uye_adi {
    font-size: 1.2rem;
}

.uye_kayit_tarihi {
    font-size: 0.8rem;
}

.uye_tel {
    margin-top: 0.5rem;
    letter-spacing: 0.1rem;
}

.uye_wp_tel {
    margin-top: 0.5rem;
    letter-spacing: 0.1rem;
}

.ilan_reklam {
    height: 25rem;
    flex: 4;
    margin-top: 1rem;
    padding: 1rem;
    box-shadow: rgba(0, 0, 0, 0.25) 0px 14px 28px, rgba(0, 0, 0, 0.22) 0px 10px 10px;
}

.ilan_aciklama_title {
    margin: 2rem 0rem 0rem 12.6rem;
    font-weight: bold;
}

.alt_bolum {
    display: flex;
    padding-left: 12.6rem;
}

.ilan_aciklama {
    width: 53.6rem;
    height: 18rem;
    margin: 0.6rem 0rem 1rem 0rem;
    padding: 0.5rem;
    box-shadow: rgba(0, 0, 0, 0.25) 0px 14px 28px, rgba(0, 0, 0, 0.22) 0px 10px 10px;
}

.ilan_aciklama_reklam {
    width: 16.5rem;
    margin: 0.6rem 0rem 1rem 1rem;
    padding: 1rem;
    box-shadow: rgba(0, 0, 0, 0.25) 0px 14px 28px, rgba(0, 0, 0, 0.22) 0px 10px 10px;

}

.mobile_fiyat:nth-child(1) {
    display: none;
}



.degisen_icerik,
.kisiyi_ara {
    display: none;
}

@media all and (max-width:932px) {
    .routerimiz{
        display: unset;
    }
    .content {
        margin: 0.2rem 0.2rem 2rem 0.2rem;
        display: grid;
        grid-template-columns: repeat(1, 100%);
        grid-template-rows: repeat(3, auto);
    }

    .ust_baslik {
        font-size: 1rem;
        padding: 0rem;
        margin:0;
        font-weight: 400;
        text-align: center;
    }

    .ilan_content {
        display: grid;
    }

    .ilan_resim_alani {
        margin-left: 0rem;
        box-shadow: none;
        margin: 0 auto; /* Yatay ortalamayı sağlar */
    }

    .ana_resim {
        width: auto;
        height: 100%;
        margin-bottom: 0;
    }

    .degisen_icerik {
        display: inline-grid;
        border-bottom: 0.1rem solid #475569;
        grid-template-columns: repeat(3, 1fr);
        grid-template-rows: repeat(1, auto);
    }

    .ilan_bilgileri {
        width: 100%;
        margin-left: 0rem;
        padding: 0rem 0.2rem 1rem 0.2rem;
        display: grid;
        grid-template-columns: repeat(2, auto);
        grid-template-rows: repeat(2, auto);
        box-shadow: rgba(0, 0, 0, 0.25) 0px 10px 20px, rgba(0, 0, 0, 0.22) 0px 8px 8px;

    }

    .ad-property {
        margin-top: 0.2rem;
        grid-row: 2/span 3;
        grid-column: 1/span 2;
        padding: 0.5rem;
    }

    .ad-property ul li {
        display: grid;
        grid-template-columns: repeat(2, auto);
        grid-template-rows: repeat(3, auto);
        border-bottom: 1px solid #eee;
        padding-top: 0.5rem;
        align-items: center;
    }

    .ad-property ul li div {
        grid-row: 1/span 2;
        align-items: center;
    }

    .ad-property ul span {
        display: column;
        text-align: right;
        align-items: center;
        /* Yükseklik olarak ortalar */
        justify-content: flex-end;
        /* Yatay olarak sağa hizalar */
    }

    .mobile_fiyat:nth-child(1) {
        display: grid;
    }

    .ad-property ul li.mobile_fiyat span {
        color: #8B0000;
        font-weight: 600;
    }

    .ilan_sahibi {
        margin: 0.5rem;
        padding: 0rem;
        box-shadow: none;
    }

    .ilan_iletisim {
        grid-row: 2;
        width: auto;
        text-align: center;
        margin-left: 0;
        padding: 0;
    }

    .uye_adi {
        font-size: 1rem;
        font-weight: 500;
    }

    .alt_bolum {
        /* bu kısım daha sonra değişen içeriğe eklenmeli */
        padding-left: 0rem;
        display: none;
    }

    .kisiyi_ara {/* ekranda sabit duracak 2 nesnenin ayarı */
        width: 100%;
        position: fixed;
        bottom: 0;
        display: flex;
        align-items: center;
        text-align: center;
        z-index: 1000;
    }

    .cepten_ara,
    .wp_ara {/* ekranda sabit duracak 2 nesne */
        width: 50%;
        height: 3rem;
        background-color: #2f3546;
        color: white;
        padding: 0.6rem 0rem;
        margin: 0rem 0.5rem 0.7rem 0.5rem;
        border-radius: 0.2rem;
    }

    .ilan_fiyat {
        display: none;
    }

    .ilan_adres {
        display: none;
    }
    .alt_resim,
    .ilan_aciklama_reklam,
    .ilan_reklam,
    .ilan_aciklama_title,
    .uye_tel,
    .uye_wp_tel {
        display: none;

    }
}
</style>




<script setup>

const vitrineItem = [
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