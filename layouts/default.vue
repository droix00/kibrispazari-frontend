<template>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css"
    integrity="sha512-DTOQO9RWCH3ppGqcWaEA1BIZOC6xxalwEsw9c2QQeAIftl+Vegovlnee1c9QX4TctnWMn13TZye+giMm8e2LwA=="
    crossorigin="anonymous" referrerpolicy="no-referrer" />
  <header class="header">
    <div class="burgerapp">
      <div class="menu-icon" @click="toggleMenu">
        <div :class="['bar', isOpen ? 'rotate1' : '']"></div>
        <div :class="['bar', isOpen ? 'hide' : '']"></div>
        <div :class="['bar', isOpen ? 'rotate2' : '']"></div>
      </div>
      <div :class="['menu', isOpen ? 'show' : '']">
        <div v-for="burgeritem in menuItems" :key="index" :style="{ transitionDelay: `${index * 0.15}s` }"
          class="menu-item">
          <a :href="burgeritem.to">
            <i :class="burgeritem.icon" class="w-4"></i>
            <span class="ml-4">{{ burgeritem.title }} </span>
            <i class="fa-solid fa-chevron-right myArrow"></i></a>
        </div>
      </div>
    </div>

    <div class="header__logo"><router-link to="Content">adapazarı</router-link></div>

    <div class="profile_icon" @click="toggleProfileMenu">
      <i class="fa-solid fa-user"></i>
      <div :class="['menu', isProfileMenuOpen ? 'show' : '']">
        <div v-for="profiliconItem in profileItem" :key="index" :style="{ transitionDelay: `${index * 0.15}s` }"
          class="menu-item">
          <a :href="profiliconItem.to">
            <i :class="profiliconItem.icon" class="w-4"></i>
            <span class="ml-4">{{ profiliconItem.title }} </span>
            <i class="fa-solid fa-chevron-right myArrow"></i>
          </a>
        </div>
      </div>
    </div>
    <div class="header__search">
      <div class="search-container">
        <input type="text" v-model="searchQuery" @input="handleSearch"
placeholder="Kelime, ilan no veya mağaza adı ile ara 2">
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
      <router-link to="profil" class="header__nav-link">Profil</router-link>
    </div>
  </header>
  <slot />
</template>
<script>

export default {
  data() {
    return {
      isOpen: false,
      isProfileMenuOpen: false,
      menuItems: [
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
        { icon: 'fa-solid fa-industry my-2', title: 'Sanayi & Parça', to: 'emlak' }
      ],
      profileItem: [
        { icon: 'fa-solid fa-gun my-2', title: 'Profil', to: 'profil' },
        { icon: 'fa-solid fa-arrow-right-to-bracket my-2', title: 'Giriş Yap', to: 'girisyap' },
        { icon: 'fa-solid fa-user-plus my-2', title: 'Kayıt Ol', to: 'hesapac' },
        { icon: 'fa-solid fa-plus my-2', title: 'Ücretsiz İlan Ver', to: 'ilanver' },
        { icon: 'fa-solid fa-arrow-right-from-bracket my-2', title: 'Çıkış Yap', to: '#' },
      ],

      searchQuery: '',/* SEARCING  INPUT KODLARI */
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
    toggleMenu() {
      this.isProfileMenuOpen = false;
      this.isOpen = !this.isOpen;
    },
    toggleProfileMenu() {
      this.isOpen = false;
      this.isProfileMenuOpen = !this.isProfileMenuOpen;
    },
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
.burgerapp,
.menu-item,
.menu-icon,
.profile_icon {
  display: none;
}


/* SERACH KODLARI */

.search-container {
  display: flex;
}

.search-container input[type="text"] {
  font-family: system-ui, Roboto, Arial, sans-serif, "Segoe UI Symbol";
  font-size: 0.9rem;
  width: 16rem;
  padding: 0.2rem 0.2rem 0.2rem 0.3rem;
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

.myArrow {
  padding: 0.6rem 0.5rem 0.5rem 0.6rem;
}

.dropdown {
  position: absolute;
  top: 2.8rem;
  /* Input alanının altına hizala */
  width: 15rem;
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
  transition: max-height 0.5s ease-out, opacity 0.5s ease-out;
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




@media all and (max-width: 932px) {
  .header {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(2, auto);
  }

  .burgerapp,
  .menu-item,
  .menu-icon,
  .profile_icon {
    display: unset;
  }

  .burgerapp {
    grid-row: 1;
    grid-column: 1/ 2;
    margin-left: 1rem;
  }

  .profile_icon {
    /* BANNERDEKİ SAĞ PROFİL İKONUDUR */
    grid-row: 1;
    grid-column: 3/ 4;
    color: white;
    justify-self: flex-end;
    font-size: 160%;
    margin-right: 1rem;
  }

  .menu-icon {
    /* BURGER İKONUDUR */
    display: flex;
    flex-direction: column;
    cursor: pointer;
    z-index: 1001;
  }

  .bar {
    /* BURGER İKONUNUN YER KAPLADIĞI ALANDIR */
    width: 23px;
    height: 2px;
    background-color: white;
    margin: 3px 0;
    transition: all 0.3s ease;
  }

  .rotate1 {
    transform: rotate(45deg);
    position: relative;
    top: 8px;
  }

  .hide {
    opacity: 0;
  }

  .rotate2 {
    transform: rotate(-45deg);
    position: relative;
    top: -8px;
  }

  .menu {
    /* AÇILAN MENÜNÜN ARKAPLANIDIR ÜSTÜNDE İSE MENÜ LİNKERLİ MEVCUTTUR */
    background-color: #333;
    position: absolute;
    top: 6rem;
    left: 0;
    transition: max-height 0.3s ease-in-out;
    overflow: hidden;
    z-index: 1000;
    opacity: 0;
    width: 100%;
    pointer-events: none;
    /* Tıklamaları etkisiz hale getirir */
  }

  .menu.show {
    max-height: 100%;
    width: 100%;
    opacity: 1;
    pointer-events: auto;
  }

  .menu-item {
    margin: 0.1rem;
    padding: 0.2rem;
    opacity: 0;
    transform: translateY(-20px);
    transition: all 0.3s ease;
    background-color: #2f3546;
    border-bottom: 1px solid gray;
    display: grid;
  }

  .menu.show .menu-item {
    opacity: 1;
    transform: translateY(0);
  }

  .menu-item a {
    color: white;
    text-decoration: none;
    padding-left: 0.5rem;
    font-size: 1rem;
    transition: color 0.3s ease;
    display: block;
  }

  .myArrow {
    float: right;
  }

  .menu-item a:hover {
    color: #ddd;
  }






















  .header__logo {
    display: inline;
    justify-content: center;
    align-items: center;
    text-align: center;
    grid-row: 1;
    margin-left: 0;
  }

  .header__search {
    width: 100%;
    background-color: white;
    grid-row: 2;
    grid-column: 1/span 3;
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
    padding: 0.6rem 0.3rem 0.1rem 0.7rem;
    cursor: pointer;
  }

  .dropdown {
    display: none;
  }

  .header__nav {
    display: none;
  }
}
</style>