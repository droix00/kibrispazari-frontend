<template>
    <!-- <header class="header">
      <div class="header__logo">LOGO</div>
      <div class="header__search">ARAMA ALANI BURASIDIR Lorem ipsum dolor sit amet.</div>
      <nav class="header__nav">
        <router-link to="ilanver" class="header__nav-link">Ücretsiz İlan Ver</router-link>
        <router-link to="girisyap" class="header__nav-link">Giriş Yap</router-link>
        <router-link to="hesapac" class="header__nav-link">Hesap Aç</router-link>       
      </nav>
    </header>  -->
  </template>

  <script>
  export default {
    name: 'Header'
  }
  </script>
  
  <style scoped>
  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #3f475f;  color:#fa6558;
    font-family:'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
  }
  
  .header__logo {
    margin-left:12.6rem;
    font-size: 2.5rem;
    /* Logo ile ilgili stil ayarları */
  }
  
  /* .header__search { */
    /* Arama alanı ile ilgili stil ayarları */
  /* } */
  
  .header__nav {
    display: flex;
    margin-right: 12.7rem;
  }
  
  .header__nav-link {
    margin-right: 1rem;
    /* Diğer linkler ile ilgili stil ayarları */
  }
  </style>
  