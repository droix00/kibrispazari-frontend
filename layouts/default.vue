<template>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css"
    integrity="sha512-DTOQO9RWCH3ppGqcWaEA1BIZOC6xxalwEsw9c2QQeAIftl+Vegovlnee1c9QX4TctnWMn13TZye+giMm8e2LwA=="
    crossorigin="anonymous" referrerpolicy="no-referrer" />
  <header class="header">
    <div class="header__logo"><router-link to="Content" class="header__nav-link">LOGO</router-link></div>
    <div class="header__search">
      <div class="search-container">
        <input type="text" v-model="searchQuery" @input="handleSearch" placeholder="Ara">
        <i class="fas fa-search" @click="handleSearch"></i>
        <div class="dropdown" v-show="isDropdownVisible">
          <ul>
            <li v-for="(item, index) in filteredItems" :key="index" @click="selectItem(item)">{{ item }}</li>
          </ul>
        </div>
      </div>
    </div>

    <nav class="header__nav">
      <router-link to="girisyap" class="header__nav-link">Giriş Yap</router-link>
      <router-link to="hesapac" class="header__nav-link">Hesap Aç</router-link>
      <router-link to="ilanver" class="header__nav-link">Ücretsiz İlan Ver</router-link>
      <router-link to="ilanver" class="header__nav-link">Profil</router-link>
    </nav>
  </header>
  <slot />

</template>
<script>
import content from '~/pages/content.vue'; // içerik bileşenini içeri aktar

export default {
  components: {
    content // içerik bileşenini kullanılabilir hale getir
  },
  
  data() {/* SEARCING  INPUT KODLARI */
    return {
      searchQuery: '',
      items: ['Emlak> Kiralık Daire', 'Emlak> Satılık Daire', 'Emlak> Villa', 'Emlak> Arazi', 'Emlak> Tarla', 'Emlak> Otel'], // Arama yapılacak öğeler
      isDropdownVisible: false
    };
  },
  computed: {
    filteredItems() {
      return this.items.filter(item =>
        item.toLowerCase().includes(this.searchQuery.toLowerCase())
      );
    }
  },
  methods: {
    handleSearch() {
      this.isDropdownVisible = this.searchQuery.length > 0;
    },
    selectItem(item) {
      this.searchQuery = item;
      this.isDropdownVisible = false;
    }
  }
};
</script>

<style scoped>
.search-container {
  position: relative;
}

.search-container input[type="text"] {
  font-family: "SHBGroteskLegacy",Roboto,sans-serif;
  font-size: 1rem;
  padding: 0.2rem 2rem 0.2rem 0.5rem;
  border-radius: 0.2rem;
  background-color: #2f3546;
  outline: none;
  color: rgba(243, 244, 246, 0.804);

}

.search-container i {
  position: absolute;
  right: 10px;
  /* Sağ tarafa hizala */
  top: 50%;
  transform: translateY(-50%);
  cursor: pointer;
}

.dropdown {
  position: absolute;
  /* Input alanının altına hizala */
  width:14.6rem;
  background-color: #2f3546;
  border-radius:0px 0px 0px 5px;
}

.dropdown ul {
  list-style: none;
}

.dropdown ul li {
  padding: 5px 10px;
  cursor: pointer;
  border-bottom: 0.5px solid #fff;color:white;
}

.dropdown ul li:hover {
  opacity: 0.5;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #3f475f;
  color: #fa6558;
  font-family: ui-sans-serif, system-ui, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
}

.header__logo {
  margin-left: 12.6rem;
  font-size: 2.5rem;
  /* Logo ile ilgili stil ayarları */
}

/* .header__search { */
/* Arama alanı ile ilgili stil ayarları */
/* } */

.header__nav {
  display: flex;
  margin-right: 11.5rem;
}

.header__nav-link {
  margin-right: 1rem;
  /* Diğer linkler ile ilgili stil ayarları */
}
</style>