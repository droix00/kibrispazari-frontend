<template>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css"
        integrity="sha512-DTOQO9RWCH3ppGqcWaEA1BIZOC6xxalwEsw9c2QQeAIftl+Vegovlnee1c9QX4TctnWMn13TZye+giMm8e2LwA=="
        crossorigin="anonymous" referrerpolicy="no-referrer" />
    <div class="content">
        <div class="ust_baslik">
            YATIRIM AMAÇLI YÜKSEK KİRA GETİRİLİ TEMİZ DAİRE SATILIKTIR
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
            <div class="ilan_bilgileri">
                <div class="ilan_fiyat">3.600.000 TL</div>
                <div class="ilan_adres">Kıbrıs / Lefkoşa / Gönyeli</div>
                <div class="ad-property">
                    <ul>
                        <li>İlan No
                            <span>1152088056</span>
                        </li>
                        <li>İlan Tarihi
                            <span>24 Ocak </span>
                        </li>
                        <li>Emlak Tipi
                            <span>Kiralık</span>
                        </li>
                        <li>m^2
                            <span>150</span>
                        </li>
                        <li>Oda Sayısı
                            <span>5</span>
                        </li>
                        <li>Bina Yaşı
                            <span>5</span>
                        </li>
                        <li>Bulunduğu Kat
                            <span>3</span>
                        </li>
                        <li>Kat Sayısı
                            <span>5</span>
                        </li>
                        <li>Isıtma
                            <span>Soba</span>
                        </li>
                        <li>Balkon
                            <span>Var</span>
                        </li>
                        <li>Asansör
                            <span>Var</span>
                        </li>
                        <li>Otopark
                            <span>Var</span>
                        </li>
                        <li>Eşyalı
                            <span>Evet</span>
                        </li>
                        <li>Aidat
                            <span>500 TL</span>
                        </li>
                        <li>Kimden
                            <span>Çelik Emlak</span>
                        </li>
                    </ul>
                </div>
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
        <!-- <div class="content__sol-reklam">Sol Reklam Alanı</div> -->
        <!-- <div class="content__sag-reklam">Sağ Reklam Alanı</div> -->
    </div>
    <myFooter />
</template>
<script>
import myFooter from '~/pages/myFooter.vue'; // footer bileşenini içeri aktar

export default {
    components: {
        myFooter // Footer bileşenini kullanılabilir hale getir
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
    padding-left: 2rem;
    padding-right: 2rem;
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

.ad-property ul li span {
    padding-left: 3rem;
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




















.content__sol-reklam {
    /* SOL REKLAM ALANI */
    flex: 1.4;
    border: 1px dashed black;
    height: 50rem;
}

.content__sag-reklam {
    /* SAĞ REKLAM ALANI */
    flex: 1.5;
    border: 1px dashed black;
    height: 50rem;
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
      ]

</script>
