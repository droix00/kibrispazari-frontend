<template>
    <div id="burgerapp">
      <header>
        <div class="menu-icon" @click="toggleMenu">
          <div :class="['bar', isOpen ? 'rotate1' : '']"></div>
          <div :class="['bar', isOpen ? 'hide' : '']"></div>
          <div :class="['bar', isOpen ? 'rotate2' : '']"></div>
        </div>
        <nav :class="['menu', isOpen ? 'show' : '']">
          <div v-for="(item, index) in menuItems" :key="index" :style="{ transitionDelay: `${index * 0.1}s` }" class="menu-item">
            <a href="#">{{ item }}</a>
          </div>
        </nav>
      </header>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        isOpen: false,
        menuItems: ['Ana Sayfa', 'Hakkında', 'İletişim']
      };
    },
    methods: {
      toggleMenu() {
        this.isOpen = !this.isOpen;
      }
    }
  };
  </script>
  
  <style scoped>
  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem;
    background-color: #333;
    color: white;
    position: relative;
  }
  
  .menu-icon {
    display: flex;
    flex-direction: column;
    cursor: pointer;
    z-index: 1001;
  }
  
  .bar {
    width: 25px;
    height: 3px;
    background-color: white;
    margin: 4px 0;
    transition: all 0.3s ease;
  }
  
  .rotate1 {
    transform: rotate(45deg);
    position: relative;
    top: 11px;
  }
  
  .hide {
    opacity: 0;
  }
  
  .rotate2 {
    transform: rotate(-45deg);
    position: relative;
    top: -11px;
  }
  
  .menu {
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: #333;
    position: absolute;
    top: 60px;
    left: 0;
    width: 100%;
    transition: max-height 0.3s ease-in-out;
    overflow: hidden;
    max-height: 0;
    z-index: 1000;
    opacity: 0;
    pointer-events: none;
  }
  
  .menu.show {
    max-height: 300px; /* Yeterli büyük bir değer verin */
    opacity: 1;
    pointer-events: auto;
  }
  
  .menu-item {
    margin: 1rem 0;
    opacity: 0;
    transform: translateY(-20px);
    transition: all 0.3s ease;
  }
  
  .menu.show .menu-item {
    opacity: 1;
    transform: translateY(0);
  }
  
  .menu-item a {
    color: white;
    text-decoration: none;
    font-size: 1.2rem;
    transition: color 0.3s ease;
  }
  
  .menu-item a:hover {
    color: #ddd;
  }
  </style>
  