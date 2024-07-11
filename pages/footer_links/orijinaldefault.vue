<template>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css"
    integrity="sha512-DTOQO9RWCH3ppGqcWaEA1BIZOC6xxalwEsw9c2QQeAIftl+Vegovlnee1c9QX4TctnWMn13TZye+giMm8e2LwA=="
    crossorigin="anonymous" referrerpolicy="no-referrer" />
  <header class="header">
    <div class="header__logo"><router-link to="Content">LOGO</router-link></div>
    <div class="header__search">
      <div class="search-container">
        <input type="text" v-model="searchQuery" @input="handleSearch"
          placeholder="Kelime, ilan no veya mağaza adı ile ara">
        <i class="fas fa-search" @click="handleSearch"></i>
        <div class="dropdown" v-show="isDropdownVisible">
          <ul>
            <li v-for="(item, index) in filteredItems" :key="index" @click="selectItem(item)">{{ item }}</li>
          </ul>
        </div>
      </div>
    </div>

    <div class="header__nav">
      <router-link to="girisyap" class="header__nav-link">Giriş Yap</router-link>
      <router-link to="hesapac" class="header__nav-link">Hesap Aç</router-link>
      <router-link to="ilanver" class="header__nav-link">Ücretsiz İlan Ver</router-link>
      <router-link to="ilanver" class="header__nav-link">Profil</router-link>
    </div>
  </header>
  <slot />
</template>
<script>
export default {
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
  display: flex;
}

.search-container input[type="text"] {
  font-family: system-ui, Roboto, Arial, sans-serif, "Segoe UI Symbol";
  font-size: 0.9rem;
  width: 16rem;
  padding: 0.2rem 0.2rem 0.2rem 0.5rem;
  border-radius: 0.2rem;
  background-color: #2f3546;
  outline: none;
  color: rgba(243, 244, 246, 0.804);
  display: flex;
  flex: 16;
}

.search-container i {
  background-color: #2f3546;
  padding: 0.38rem;
  border-radius: 0rem .2rem .2rem 0rem;
  cursor: pointer;
  flex: 1;
}

.dropdown {
  position: absolute;
  /* Input alanının altına hizala */
  width: 14.6rem;
  background-color: #2f3546;
  border-radius: 0px 0px 0px 5px;
}

.dropdown ul {
  list-style: none;
}

.dropdown ul li {
  padding: 5px 10px;
  cursor: pointer;
  border-bottom: 0.5px solid #fff;
  color: white;
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


@media all and (max-width: 768px) {
  .header {
    flex-direction: column;
    align-items: flex-start;
  }

  .header__logo {
    display: inline;
    margin-left: 0.2rem;
  }

  .header__search {
    width: 100%;
    background-color: white;
  }

  .search-container input[type="text"] {
    width: 100%;
    height: 2.3rem;
    background-color: white;
    border-bottom: 1px solid black;
    outline: none;
    border-radius: 0;
    color: black;
    padding-left: 1.2rem;
  }

  .search-container i {
    background-color: #2f3546;
    border-radius: 0;
    padding: 0.6rem 0.1rem 0.1rem 0.7rem;
    cursor: pointer;
  }

  .dropdown {
    display: none;
  }

  .header__nav {
    display: none;
  }
}

/* 
@media all and (max-width:768px) {
  .header__logo {
    display: inline;
    margin-left: 1.20rem;
  }

  .search-container {
    display: none;
  }

  .header__nav-link {
    display: none;
  }
}

.search-container {
  position: relative;
} */
</style>