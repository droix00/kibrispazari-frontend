<template>

  <div class="content rounded-lg">
    <p class="text-2xl px-4 py-3 bg-lime">Adım adım ilanınızı seçelim</p>
    <UBreadcrumb :links="myBreadCrumb" class="text-2xl ml-4 mb-4 bg-lime" />

    <UPageGrid class="grid_properties">
      <UPageCard v-for="(module, index) in modules" :key="index" v-bind="module" target="_self">
        <template #icon>
          <span class="m-auto"><i :class="module.icon"></i></span>
        </template>
        <template #title>
          <span class="m-auto">{{ module.title }}</span>
        </template>
      </UPageCard>
    </UPageGrid>
    <p class="text-base px-4 py-4">Daha iyi bir kitleye ulaşmak için en ilgili kategoriyi seçiniz </p>
    <p class="text-base px-4">İlan paylaşım kuralları için <a href="#" class="text-red-500">tıklayınız</a> </p>
  </div>
  <myFooter />
</template>


<style scoped>
.content {
  box-shadow: rgba(0, 0, 0, 0.25) 0px 14px 28px, rgba(0, 0, 0, 0.22) 0px 10px 10px;
  margin: 2rem 11.8rem 3rem 12.8rem;
  padding: 1rem 2rem 2rem 2rem;
}

.grid_properties {
  display: grid;
  grid-template-columns: repeat(4, minmax(0, 1fr));
  margin: 0rem 2rem;
}


@media all and (max-width:768px) {
  .content {
    margin: 0.5rem 0.2rem 3rem 0.25rem;
    padding: 0rem 0rem 1rem 0rem;
  }

  .grid_properties {
    grid-template-columns: repeat(2, minmax(0, 1fr));
    margin: 0.4rem;
    gap: 0.5rem;
  }
}
</style>
<script setup lang="ts">
import myFooter from '~/pages/myFooter.vue'; // Header bileşenini içeri aktar

const modules = [{
  title: 'Acil Acil',
  to: 'emlak',
  icon: 'fa-solid fa-clock fa-2xl'
}, {
  title: 'Emlak',
  to: 'https://github.com/nuxt-community/eslint-module',
  icon: 'fa-solid fa-house fa-2xl'
}, {
  title: 'Araba',
  to: 'https://github.com/nuxt-modules/tailwindcss',
  icon: 'fa-solid fa-car fa-2xl'
}, {
  title: 'Telefon',
  to: 'https://github.com/nuxt-modules/tailwindcss',
  icon: 'fa-solid fa-mobile-screen-button fa-2xl'
}, {
  title: 'Bilgisayar',
  to: 'https://github.com/nuxt-modules/tailwindcss',
  icon: 'fa-solid fa-laptop fa-2xl'
}, {
  title: 'Elektronik',
  to: 'https://github.com/nuxt-modules/tailwindcss',
  icon: 'fa-solid fa-plug fa-2xl'
}, {
  title: 'Ev Araçları',
  to: 'https://github.com/nuxt-modules/tailwindcss',
  icon: 'fa-solid fa-tree-city fa-2xl'
}, {
  title: 'Bölüm Araçları',
  to: 'https://github.com/nuxt-modules/tailwindcss',
  icon: 'fa-solid fa-graduation-cap fa-2xl'
}, {
  title: 'Özel Ders',
  to: 'https://github.com/nuxt-modules/tailwindcss',
  icon: 'fa-solid fa-brain fa-2xl'
}, {
  title: 'İş İlanları',
  to: 'https://github.com/nuxt-modules/tailwindcss',
  icon: 'fa-solid fa-briefcase fa-2xl'
}, {
  title: 'Sanayi & Parça',
  to: 'https://github.com/nuxt-modules/tailwindcss',
  icon: 'fa-solid fa-industry fa-2xl'
}]

const myBreadCrumb = [{
  label: 'Anasayfa',
  icon: 'i-heroicons-home',
  to: '/'
}, {
  label: 'İlan Ver',
  icon: 'i-heroicons-square-3-stack-3d',
  to: '/'
}, {
  label: 'Breadcrumb',
  icon: 'i-heroicons-link',
  to: '/'
}]
</script>
