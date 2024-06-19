<script setup lang="ts">
const modules = [{
  title: 'Kiralık Daire',
  to: 'emlak_ilan',
  icon: 'fa-solid fa-house-user fa-2xl'
}, {
  title: 'Satılık Daire',
  to: 'https://github.com/nuxt-community/eslint-module',
  icon: 'fa-solid fa-house-circle-check fa-2xl'
}, {
  title: 'Günlük Kiralık',
  to: 'https://github.com/nuxt-community/eslint-module',
  icon: 'fa-solid fa-house-flag fa-2xl'
}, {
  title: 'Villa',
  to: 'https://github.com/nuxt-modules/tailwindcss',
  icon: 'fa-solid fa-house-chimney fa-2xl'
}, {
  title: 'Kiralık İşyeri',
  to: 'https://github.com/nuxt-modules/tailwindcss',
  icon: 'fa-solid fa-shop fa-2xl'
}, {
  title: 'Satılık İşyeri',
  to: 'https://github.com/nuxt-modules/tailwindcss',
  icon: 'fa-solid fa-dollar-sign fa-2xl'
}, {
  title: 'Kiralık Arazi',
  to: 'https://github.com/nuxt-modules/tailwindcss',
  icon: 'fa-solid fa-map-marked-alt fa-2xl'
}, {
  title: 'Satılık Arazi',
  to: 'https://github.com/nuxt-modules/tailwindcss',
  icon: 'fa-solid fa-tractor fa-2xl' //fa-tree-city
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

<template>

  <div class="content rounded-lg">
    <p class="text-2xl px-4 py-3 bg-lime">Adım adım ilanınızı seçelim</p>
    
      <UBreadcrumb :links="myBreadCrumb" class="text-2xl ml-4 mb-4 bg-lime"/>
    
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

.grid-container {
  display: flex;
  height: 10rem;
  gap: 1rem;
  margin: 2rem 11.8rem 3rem 12.8rem;
  /* İstenilen boşluk değeri */
}
</style>
