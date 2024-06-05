<template>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css"
    integrity="sha512-DTOQO9RWCH3ppGqcWaEA1BIZOC6xxalwEsw9c2QQeAIftl+Vegovlnee1c9QX4TctnWMn13TZye+giMm8e2LwA=="
    crossorigin="anonymous" referrerpolicy="no-referrer" />
  <div class="content">
    <div class="content__menu">
      <h2 class="content__menu-title">Kategoriler</h2>
      <ul class="content__menu-list">
        <li class="content__menu-item">
          <router-link to="/acil-acil" class="content__menu-link"><i class="fa-solid fa-clock"></i> Acil
            Acil</router-link>
        </li>
        <li class="content__menu-item">
          <router-link to="/acil-acil" class="content__menu-link"><i class="fa-solid fa-chart-line"></i> Fiyatı
            Düşenler</router-link>
        </li>
        <li class="content__menu-item">
          <router-link to="/araba" class="content__menu-link"><i class="fa-solid fa-house-flag"></i> Emlak</router-link>
        </li>
        <li class="content__menu-item">
          <router-link to="/konut" class="content__menu-link"><i class="fa-solid fa-car"></i> Araba</router-link>
        </li>
        <li class="content__menu-item">
          <router-link to="/telefon" class="content__menu-link"><i class="fa-solid fa-mobile-screen-button"></i>
            Telefon</router-link>
        </li>
        <li class="content__menu-item">
          <router-link to="/bilgisayar" class="content__menu-link"><i class="fa-solid fa-laptop"></i>
            Bilgisayar</router-link>
        </li>
        <li class="content__menu-item">
          <router-link to="/elektronik" class="content__menu-link"><i class="fa-solid fa-plug"></i>
            Elektronik</router-link>
        </li>
        <li class="content__menu-item">
          <router-link to="/ev-araclari" class="content__menu-link"><i class="fa-solid fa-tree-city"></i> Ev
            Araçları</router-link>
        </li>
        <li class="content__menu-item">
          <router-link to="/bolum-araclari" class="content__menu-link"><i class="fa-solid fa-graduation-cap"></i> Bölüm
            Araçları</router-link>
        </li>
        <li class="content__menu-item">
          <router-link to="/ozel-ders" class="content__menu-link"><i class="fa-solid fa-brain"></i> Özel
            Ders</router-link>
        </li>
        <li class="content__menu-item">
          <router-link to="/is-ilanlari" class="content__menu-link"><i class="fa-solid fa-briefcase"></i> İş
            İlanları</router-link>
        </li>
        <li class="content__menu-item">
          <router-link to="/sanayi-ve-yedek-parca" class="content__menu-link"><i class="fa-solid fa-industry"></i>
            Sanayi
            & Parça</router-link>
        </li>
      </ul>
    </div>
    <div class="content__vitrine">
      <h2 class="content__vitrine-title">Anasayfa Vitrini</h2>
      <div class="content__vitrine-grid">
        <!-- Buraya dinamik olarak içerik ekleyebilirsiniz -->
        <!-- Her satıra 5 adet kutu ekleyebilirsiniz -->

        <div v-for="item in vitrineItem.slice(0, 35)" :key="item.id" class="content__vitrine-item">
          <a :href="'/' + item.link">
            <img :src="item.image" alt="Resim">
            <div class="ilan_fiyat">500TL</div>
            <p>{{ item.description }}</p>
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
              <div class="ilan_fiyat">500TL</div>
              <p>{{ item.description }}</p>
            </a>
          </div>
        </div>
      </div>
    </div>

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
const vitrineItem = [
  { id: 1, image: 'a.jpg', description: 'Açıklama 1', link: 'ilan' },
  { id: 2, image: 'b.jpg', description: 'Açıklama 2', link: 'girisyap' },
  { id: 3, image: 'buyuk-resim.jpg', description: 'Açıklama 3', link: 'ilan' },
  { id: 4, image: 'c.jpg', description: 'Açıklama 4', link: 'ilan' },
  { id: 5, image: 'c.jpg', description: 'Açıklama 5', link: 'ilan' },
  { id: 6, image: 'c.jpg', description: 'Açıklama 6', link: 'ilan' },
  { id: 7, image: 'c.jpg', description: 'Açıklama 7', link: 'ilan' },
  { id: 8, image: 'c.jpg', description: 'Açıklama 8', link: 'ilan' },
  { id: 9, image: 'c.jpg', description: 'Açıklama 9', link: 'ilan' },
  { id: 10, image: 'c.jpg', description: 'Açıklama 10', link: 'ilan' },
  { id: 11, image: 'c.jpg', description: 'Açıklama 11', link: 'ilan' },
  { id: 12, image: 'c.jpg', description: 'Açıklama 12', link: 'ilan' },
  { id: 13, image: 'c.jpg', description: 'Açıklama 13', link: 'ilan' },
  { id: 14, image: 'c.jpg', description: 'Açıklama 14', link: 'ilan' },
  { id: 15, image: 'c.jpg', description: 'Açıklama 15', link: 'ilan' },
  { id: 16, image: 'c.jpg', description: 'Açıklama 16', link: 'ilan' },
  { id: 17, image: 'c.jpg', description: 'Açıklama 17', link: 'ilan' },
  { id: 18, image: 'c.jpg', description: 'Açıklama 18', link: 'ilan' },
  { id: 19, image: 'c.jpg', description: 'Açıklama 19', link: 'ilan' },
  { id: 20, image: 'c.jpg', description: 'Açıklama 20', link: 'ilan' },
  { id: 21, image: 'c.jpg', description: 'Açıklama 21', link: 'ilan' },
  { id: 22, image: 'c.jpg', description: 'Açıklama 22', link: 'ilan' },
  { id: 23, image: 'c.jpg', description: 'Açıklama 23', link: 'ilan' },
  { id: 24, image: 'c.jpg', description: 'Açıklama 24', link: 'ilan' },
  { id: 25, image: 'c.jpg', description: 'Açıklama 25', link: 'ilan' },
  { id: 26, image: 'c.jpg', description: 'Açıklama 26', link: 'ilan' },
  { id: 27, image: 'c.jpg', description: 'Açıklama 27', link: 'ilan' },
  { id: 28, image: 'c.jpg', description: 'Açıklama 28', link: 'ilan' },
  { id: 29, image: 'c.jpg', description: 'Açıklama 29', link: 'ilan' },
  { id: 30, image: 'c.jpg', description: 'Açıklama 30', link: 'ilan' },
  { id: 31, image: 'c.jpg', description: 'Açıklama 31', link: 'ilan' },
  { id: 32, image: 'c.jpg', description: 'Açıklama 32', link: 'ilan' },
  { id: 33, image: 'c.jpg', description: 'Açıklama 33', link: 'ilan' },
  { id: 34, image: 'c.jpg', description: 'Açıklama 34', link: 'ilan' },
  { id: 35, image: 'c.jpg', description: 'Açıklama 35', link: 'ilan' },
  { id: 36, image: 'c.jpg', description: 'Açıklama 36', link: 'ilan' },
  { id: 37, image: 'c.jpg', description: 'Açıklama 37', link: 'ilan' },
  { id: 38, image: 'c.jpg', description: 'Açıklama 38', link: 'ilan' },
  { id: 39, image: 'c.jpg', description: 'Açıklama 39', link: 'ilan' },
  { id: 40, image: 'c.jpg', description: 'Açıklama 40', link: 'ilan' },
  { id: 41, image: 'c.jpg', description: 'Açıklama 41', link: 'ilan' },
  { id: 42, image: 'c.jpg', description: 'Açıklama 42', link: 'ilan' },
  { id: 43, image: 'c.jpg', description: 'Açıklama 43', link: 'ilan' },
  { id: 44, image: 'c.jpg', description: 'Açıklama 44', link: 'ilan' },
  { id: 45, image: 'c.jpg', description: 'Açıklama 45', link: 'ilan' },
  { id: 46, image: 'c.jpg', description: 'Açıklama 46', link: 'ilan' },
  { id: 47, image: 'c.jpg', description: 'Açıklama 47', link: 'ilan' },
  { id: 48, image: 'c.jpg', description: 'Açıklama 48', link: 'ilan' },
  { id: 49, image: 'c.jpg', description: 'Açıklama 49', link: 'ilan' },
  { id: 50, image: 'c.jpg', description: 'Açıklama 50', link: 'ilan' },
  { id: 51, image: 'c.jpg', description: 'Açıklama 51', link: 'ilan' },
  { id: 52, image: 'c.jpg', description: 'Açıklama 52', link: 'ilan' },
  { id: 53, image: 'c.jpg', description: 'Açıklama 53', link: 'ilan' },
  { id: 54, image: 'c.jpg', description: 'Açıklama 54', link: 'ilan' },
  { id: 55, image: 'c.jpg', description: 'Açıklama 55', link: 'ilan' },
]
</script>

<style scoped>
.content {
  /*Content alanı */
  display: flex;
  margin:0rem 12.2rem 2rem 12.8rem;
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
  grid-template-columns: repeat(5, 0fr);
  gap: 1rem;
  margin-left: 1.2rem;
}

.content__vitrine-item {
  /* anasayfa vitrinindeki her ürünün ayarı*/
  border: 1px solid #ccc;
  padding: 0rem;
  width: 11.1rem;
}

.ilan_fiyat {
  height: 1.6rem;
  display: flex;
  justify-content: center;
  background-color: #dbdbdb61;
}

.content__vitrine-item img {
  /* anasayfa vitrinindeki her ürünün resim ayarı */
  width: 11.1rem;
  height: 9rem;
  background-size: cover;
  flex-wrap: wrap;
  /* height: auto; */
}

.content__vitrine-item p {
  /* anasayfa vitrinindeki her ürünün alt metin ayarı */
  margin: 0.2rem;
}
</style>
