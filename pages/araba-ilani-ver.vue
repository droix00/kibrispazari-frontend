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
  title: 'ATV',
  to: 'ilan-ver-detay',
  icon: 'fa-solid fa-truck-monster fa-2xl'
}, {
  title: 'Bisiklet',
  to: 'ilan-ver-detay',
  icon: 'fa-solid fa-person-biking fa-2xl'
}, {
  title: 'Deniz Araçları',
  to: 'ilan-ver-detay',
  icon: 'fa-solid fa-ship fa-2xl'
}, {
  title: 'Karavan',
  to: 'ilan-ver-detay',
  icon: 'fa-solid fa-caravan fa-2xl'
}, {
  title: 'Kiralık Araç',
  to: 'ilan-ver-detay',
  icon: 'fa-solid fa-hand-holding-dollar fa-2xl'
}, {
  title: 'Minivan, Van, Panelvan',
  to: 'ilan-ver-detay',
  icon: 'fa-solid fa-van-shuttle fa-2xl'
}, {
  title: 'Motorsiklet',
  to: 'ilan-ver-detay',
  icon: 'fa-solid fa-motorcycle fa-2xl'
}, {
  title: 'Otomobil',
  to: 'ilan-ver-detay',
  icon: 'fa-solid fa-car fa-2xl' //fa-tree-city
}, {
  title: 'SUV, 4X4, Pick-up',
  to: 'ilan-ver-detay',
  icon: 'fa-solid fa-truck-pickup fa-2xl' //fa-tree-city
}, {
  title: 'Ticari Araç',
  to: 'ilan-ver-detay',
  icon: 'fa-solid fa-taxi fa-2xl' //fa-tree-city
}, {
  title: 'Tarım Araçları',
  to: 'ilan-ver-detay',
  icon: 'fa-solid fa-tractor fa-2xl' //fa-tree-city
}]
</script>