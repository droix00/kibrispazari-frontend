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

const myBreadCrumb = [{
  label: 'Anasayfa',
  icon: 'i-heroicons-home',
  to: 'ilan-ver-detay'
}, {
  label: 'İlan Ver',
  icon: 'i-heroicons-square-3-stack-3d',
  to: 'ilan-ver-detay'
}, {
  label: 'Breadcrumb',
  icon: 'i-heroicons-link',
  to: '/'
}]

const modules = [{
  title: 'Kiralık Daire',
  to: 'ilan-ver-detay',
  icon: 'fa-solid fa-house-user fa-2xl'
}, {
  title: 'Satılık Daire',
  to: 'ilan-ver-detay',
  icon: 'fa-solid fa-house-circle-check fa-2xl'
}, {
  title: 'Günlük Kiralık',
  to: 'ilan-ver-detay',
  icon: 'fa-solid fa-house-flag fa-2xl'
}, {
  title: 'Villa',
  to: 'ilan-ver-detay',
  icon: 'fa-solid fa-house-chimney fa-2xl'
}, {
  title: 'Kiralık İşyeri',
  to: 'ilan-ver-detay',
  icon: 'fa-solid fa-shop fa-2xl'
}, {
  title: 'Satılık İşyeri',
  to: 'ilan-ver-detay',
  icon: 'fa-solid fa-dollar-sign fa-2xl'
}, {
  title: 'Kiralık Arazi',
  to: 'ilan-ver-detay',
  icon: 'fa-solid fa-map-marked-alt fa-2xl'
}, {
  title: 'Satılık Arazi',
  to: 'ilan-ver-detay',
  icon: 'fa-solid fa-tractor fa-2xl' //fa-tree-city
}]
</script>