<template>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <div class="content">
    <div class="sol_reklam_alani"></div>
    <div class="content__menu">
      <h2 class="content__menu-title">Kategoriler</h2>
      <ul class="content__menu-list">
        <li class="content__menu-item">
          <div v-for="item in solMenu" :key="index">
            <span class="m-auto"><i :class="item.icon"></i></span>
            <a :href="item.to" class="hover:text-gray-600 hover:underline underline-offset-1 ml-2"> {{ item.title }}</a>
          </div>
        </li>
      </ul>
    </div>
    <div class="content__vitrine">
      <h2 class="content__vitrine-title">Anasayfa Vitrini</h2>
      <div class="content__vitrine-grid">
        <!-- Buraya dinamik olarak içerik ekleyebilirsiniz -->

        <div v-for="item in vitrineItem.slice(0, 35)" :key="item.id" class="content__vitrine-item hover:bg-blue-50">
          <a :href="'/' + item.link">
            <img :src="item.image" alt="Resim">
            <div class="ilan_fiyat">{{ item.price }} TL</div>
            <p class="text-sm p-1" style="overflow: hidden;text-overflow: ellipsis;white-space: nowrap;">{{
            item.description }}</p>
          </a>
        </div>
      </div>

      <div class="content__vitrine">
        <h2 class="content__vitrine-title">Son Eklenenler</h2>
        <div class="content__vitrine-grid">
          <!-- Buraya dinamik olarak içerik ekleyebilirsiniz -->
          <!-- Her satıra 5 adet kutu ekleyebilirsiniz -->
          <div v-for="item in vitrineItem.slice(35, 55)" :key="item.id" class="content__vitrine-item">
            <a :href="'/' + item.link">
              <img :src="item.image" alt="Resim">
              <div class="ilan_fiyat">{{ item.price }} TL</div>
              <p>{{ item.description }}</p>
            </a>
          </div>
        </div>
      </div>
    </div>
    <div class="sag_reklam_alani"></div>
  </div>
  <myFooter />
</template>
<script>
import myFooter from '~/pages/myFooter.vue'; // Header bileşenini içeri aktar
export default {
  components: {
    myFooter // Footer bileşenini kullanılabilir hale getir
  }
}
</script>

<script setup>
const solMenu = [
  { icon: 'fa-solid fa-clock mb-2', title: 'Acil Acil', to: 'ilanlar' },
  { icon: 'fa-solid fa-chart-line my-2', title: 'Fiyatı Düşenler', to: 'ilanlar' },
  { icon: 'fa-solid fa-house-flag my-2', title: 'Emlak', to: 'ilanlar' },
  { icon: 'fa-solid fa-car my-2', title: 'Araba', to: 'ilanlar' },
  { icon: 'fa-solid fa-mobile-screen-button my-2', title: 'Telefon', to: 'ilanlar' },
  { icon: 'fa-solid fa-laptop my-2', title: 'Bilgisayar', to: 'ilanlar' },
  { icon: 'fa-solid fa-plug my-2', title: 'Elektronik', to: 'ilanlar' },
  { icon: 'fa-solid fa-tree-city my-2', title: 'Ev Araçları', to: 'emlak' },
  { icon: 'fa-solid fa-graduation-cap my-2', title: 'Bölüm Araçları', to: 'emlak' },
  { icon: 'fa-solid fa-brain my-2', title: 'Özel Ders', to: 'emlak' },
  { icon: 'fa-solid fa-briefcase my-2', title: 'İş İlanları', to: 'emlak' },
  { icon: 'fa-solid fa-industry my-2', title: 'Sanayi & Parça', to: 'emlak' },
]

const vitrineItem = [
  { id: 1, image: 'a.jpg', description: 'BMW 318i 2007 tertemiz satılık', link: 'ilan_bilgileri', price: 100 },
  { id: 2, image: 'b.jpg', description: 'Audi A4 sahibinden satılıktır', link: 'ilan_bilgileri', price: 200 },
  { id: 3, image: 'buyuk-resim.jpg', description: 'Açıklama 3 olarak ifade edilen bir ağaçta tütmüş ', link: 'ilan_bilgileri', price: 300 },
  { id: 4, image: 'c.jpg', description: 'Açıklama 4', link: 'ilan_bilgileri', price: 400 },
  { id: 5, image: 'c.jpg', description: 'Açıklama 5', link: 'ilan_bilgileri', price: 500 },
  { id: 6, image: 'c.jpg', description: 'Açıklama 6', link: 'ilan_bilgileri', price: 600 },
  { id: 7, image: 'c.jpg', description: 'Açıklama 7', link: 'ilan_bilgileri', price: 700 },
  { id: 8, image: 'c.jpg', description: 'Açıklama 8', link: 'ilan_bilgileri', price: 800 },
  { id: 9, image: 'c.jpg', description: 'Açıklama 9', link: 'ilan_bilgileri', price: 900 },
  { id: 10, image: 'c.jpg', description: 'Açıklama 10', link: 'ilan_bilgileri', price: 100 },
  { id: 11, image: 'c.jpg', description: 'Açıklama 11', link: 'ilan_bilgileri', price: 200 },
  { id: 12, image: 'c.jpg', description: 'Açıklama 12', link: 'ilan_bilgileri', price: 300 },
  { id: 13, image: 'c.jpg', description: 'Açıklama 13', link: 'ilan_bilgileri', price: 400 },
  { id: 14, image: 'c.jpg', description: 'Açıklama 14', link: 'ilan_bilgileri', price: 500 },
  { id: 15, image: 'c.jpg', description: 'Açıklama 15', link: 'ilan_bilgileri', price: 600 },
  { id: 16, image: 'c.jpg', description: 'Açıklama 16', link: 'ilan', price: 800 },
  { id: 17, image: 'c.jpg', description: 'Açıklama 17', link: 'ilan', price: 400 },
  { id: 18, image: 'c.jpg', description: 'Açıklama 18', link: 'ilan', price: 300 },
  { id: 19, image: 'c.jpg', description: 'Açıklama 19', link: 'ilan', price: 300 },
  { id: 20, image: 'c.jpg', description: 'Açıklama 20', link: 'ilan', price: 300 },
  { id: 21, image: 'c.jpg', description: 'Açıklama 21', link: 'ilan', price: 300 },
  { id: 22, image: 'c.jpg', description: 'Açıklama 22', link: 'ilan', price: 300 },
  { id: 23, image: 'c.jpg', description: 'Açıklama 23', link: 'ilan', price: 300 },
  { id: 24, image: 'c.jpg', description: 'Açıklama 24', link: 'ilan', price: 300 },
  { id: 25, image: 'c.jpg', description: 'Açıklama 25', link: 'ilan', price: 300 },
  { id: 26, image: 'c.jpg', description: 'Açıklama 26', link: 'ilan', price: 300 },
  { id: 27, image: 'c.jpg', description: 'Açıklama 27', link: 'ilan', price: 300 },
  { id: 28, image: 'c.jpg', description: 'Açıklama 28', link: 'ilan', price: 300 },
  { id: 29, image: 'c.jpg', description: 'Açıklama 29', link: 'ilan', price: 300 },
  { id: 30, image: 'c.jpg', description: 'Açıklama 30', link: 'ilan', price: 300 },
  { id: 31, image: 'c.jpg', description: 'Açıklama 31', link: 'ilan', price: 300 },
  { id: 32, image: 'c.jpg', description: 'Açıklama 32', link: 'ilan', price: 300 },
  { id: 33, image: 'c.jpg', description: 'Açıklama 33', link: 'ilan', price: 300 },
  { id: 34, image: 'c.jpg', description: 'Açıklama 34', link: 'ilan', price: 300 },
  { id: 35, image: 'c.jpg', description: 'Açıklama 35', link: 'ilan', price: 300 },
  { id: 36, image: 'c.jpg', description: 'Açıklama 36', link: 'ilan', price: 400 },
  { id: 37, image: 'c.jpg', description: 'Açıklama 37', link: 'ilan', price: 500 },
  { id: 38, image: 'c.jpg', description: 'Açıklama 38', link: 'ilan', price: 600 },
  { id: 39, image: 'c.jpg', description: 'Açıklama 39', link: 'ilan', price: 700 },
  { id: 40, image: 'c.jpg', description: 'Açıklama 40', link: 'ilan', price: 800 },
  { id: 41, image: 'c.jpg', description: 'Açıklama 41', link: 'ilan', price: 900 },
  { id: 42, image: 'c.jpg', description: 'Açıklama 42', link: 'ilan', price: 300 },
  { id: 43, image: 'c.jpg', description: 'Açıklama 43', link: 'ilan', price: 300 },
  { id: 44, image: 'c.jpg', description: 'Açıklama 44', link: 'ilan', price: 300 },
  { id: 45, image: 'c.jpg', description: 'Açıklama 45', link: 'ilan', price: 300 },
  { id: 46, image: 'c.jpg', description: 'Açıklama 46', link: 'ilan', price: 300 },
  { id: 47, image: 'c.jpg', description: 'Açıklama 47', link: 'ilan', price: 300 },
  { id: 48, image: 'c.jpg', description: 'Açıklama 48', link: 'ilan', price: 300 },
  { id: 49, image: 'c.jpg', description: 'Açıklama 49', link: 'ilan', price: 300 },
  { id: 50, image: 'c.jpg', description: 'Açıklama 50', link: 'ilan', price: 300 },
  { id: 51, image: 'c.jpg', description: 'Açıklama 51', link: 'ilan', price: 300 },
  { id: 52, image: 'c.jpg', description: 'Açıklama 52', link: 'ilan', price: 300 },
  { id: 53, image: 'c.jpg', description: 'Açıklama 53', link: 'ilan', price: 300 },
]
</script>

<style scoped>
.content {
  /*Content alanı */
  display: flex;
  /* margin: 0rem 12.2rem 2rem 12.8rem; */
}

.sol_reklam_alani {
  flex: 1.48;
}

.sag_reklam_alani {
  flex: 1.45;
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
  flex: 7;
  padding: 1rem 0rem;
}

.content__vitrine-title {
  margin-bottom: 1rem;
  /*anasayfa vitrini yazısı ayarı */
  font-weight: bold;
  margin-left: 1.2rem;
}

.content__vitrine-grid {
  /* anasayfa vitrini gridi */
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(11rem, 1fr));
  /* Önerilen değişiklik: minmax() fonksiyonu kullanarak esneklik sağlanıyor */
  gap: 1rem;
  margin-left: 1.2rem;
}

.content__vitrine-item {
  border: 1px solid #ccc;
  padding: 0rem;
  width: 11.1;
  /* Önerilen değişiklik: Yüzde olarak genişlik hesaplaması */
  max-width: 100%;
  /* Maksimum genişlik belirlenerek öğelerin çok genişlemesi önleniyor */
}

.ilan_fiyat {
  height: 1.6rem;
  display: flex;
  justify-content: center;
  background-color: #dbdbdb61;
}

.content__vitrine-item img {
  /* anasayfa vitrinindeki her ürünün resim ayarı */
  width: 100%;
  height: 9rem;
  background-size: cover;
  flex-wrap: wrap;
  /* height: auto; */
}

.content__vitrine-item p {
  /* anasayfa vitrinindeki her ürünün alt metin ayarı */
  margin: 0.2rem;
}

@media all and (max-width:932px) {

  /* MOBİL CİHAZ AYARLARI KODLARI */
  .sol_reklam_alani,
  .sag_reklam_alani,
  .content__menu {
    display: none;
  }

  .content__vitrine-grid {
    margin-right: 1.2rem;
  }
}
@media all and (max-width:410px) {


  .content__vitrine-title {
  /*anasayfa vitrini yazısı ayarı */
  font-weight: bold;
  margin-left: 0.2rem;
}

.content__vitrine-grid {
  /* anasayfa vitrini gridi */
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(45%, 1fr));
  /* Önerilen değişiklik: minmax() fonksiyonu kullanarak esneklik sağlanıyor */
  gap: 0.4rem;
  margin-left: 0.2rem;
  margin-right: 0.2rem;
}

}
</style>
