<script setup lang="ts">
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
    <UBreadcrumb :links="myBreadCrumb" class="text-2xl ml-4 mb-4 bg-lime" />
    <div class="emlak_detaylar">
      <div class="mt_kare">
        <p class="text-sm font-semibold text-gray-500">m^2</p>
                <input class="mt-1 rounded border py-1 px-3 text-lg shadow" />
      </div>
      <div class="oda_sayisi">
        <p class="text-sm font-semibold text-gray-500">Oda Sayısı</p>
        <UButton class="mx-1 my-2 p-3">1</UButton>
        <UButton class="mx-1 my-0 p-3">1</UButton>
        <UButton class="mx-1 my-0 p-3">3</UButton>
        <UButton class="mx-1 my-2 p-3">4</UButton>
        <UButton class="mx-1 my-2 p-3">5</UButton>
        <UButton class="mx-1 my-2 p-3">6</UButton>
        <UButton class="mx-1 my-2 p-3">Özel</UButton>
      </div>
      <div class="bina_yasi">
        <p class="text-sm font-semibold text-gray-500">Bina Yaşı</p>
        <UButton class="mx-1 my-2 p-3">1</UButton>
        <UButton class="mx-1 my-2 p-3">2</UButton>
        <UButton class="mx-1 my-2 p-3">3</UButton>
        <UButton class="mx-1 my-2 p-3">4</UButton>
        <UButton class="mx-1 my-2 p-3">5</UButton>
        <UButton class="mx-1 my-2 p-3">6</UButton>
        <UButton class="mx-1 my-2 p-3">Özel</UButton>

      </div>
      <div class="bulundugu_kat">
        <p class="text-sm font-semibold text-gray-500">Bulunduğu Kat</p>
        <UButton class="mx-1 my-2 p-3">1</UButton>
        <UButton class="mx-1 my-2 p-3">2</UButton>
        <UButton class="mx-1 my-2 p-3">3</UButton>
        <UButton class="mx-1 my-2 p-3">4</UButton>
        <UButton class="mx-1 my-2 p-3">5</UButton>
        <UButton class="mx-1 my-2 p-3">6</UButton>
        <UButton class="mx-1 my-2 p-3">Özel</UButton>
      </div>
      <div class="kat_sayisi">
        <p class="text-sm font-semibold text-gray-500">Kat Sayısı</p>
        <UButton class="mx-1 my-2 p-3">1</UButton>
        <UButton class="mx-1 my-2 p-3">2</UButton>
        <UButton class="mx-1 my-2 p-3">3</UButton>
        <UButton class="mx-1 my-2 p-3">4</UButton>
        <UButton class="mx-1 my-2 p-3">5</UButton>
        <UButton class="mx-1 my-2 p-3">6</UButton>
        <UButton class="mx-1 my-2 p-3">Özel</UButton>
      </div>
      <div class="isitma">
        <p class="text-sm font-semibold text-gray-500">Isıtma</p>
        <UButton class="mx-1 my-2 p-3">Kombi</UButton>
        <UButton class="mx-1 my-2 p-3">Soba</UButton>
        <UButton class="mx-1 my-2 p-3">Doğalgaz</UButton>
        <UButton class="mx-1 my-2 p-3">Özel</UButton>
      </div>
      <div class="balkon">
        <p class="text-sm font-semibold text-gray-500">Balkon</p>
        <UButton class="mx-1 my-2 p-3">Var</UButton>
        <UButton class="mx-1 my-2 p-3">Yok</UButton>
      </div>
      <div class="asansor">
        <p class="text-sm font-semibold text-gray-500">Asansör</p>
        <UButton class="mx-1 my-2 p-3">Var</UButton>
        <UButton class="mx-1 my-2 p-3">Yok</UButton>
      </div>
      <div class="otopark">
        <p class="text-sm font-semibold text-gray-500">Otopark</p>
        <UButton class="mx-1 my-2 p-3">Var</UButton>
        <UButton class="mx-1 my-2 p-3">Yok</UButton>
      </div>
      <div class="esya">
        <p class="text-sm font-semibold text-gray-500">Eşyalı</p>
        <UButton class="mx-1 my-2 p-3">Evet</UButton>
        <UButton class="mx-1 my-2 p-3">Hayır</UButton>
      </div>
      <div class="aidat">
        <p class="text-sm font-semibold text-gray-500">Aidat</p>
        <UButton class="mx-1 my-2 p-3">Kendisi</UButton>
        <UButton class="mx-1 my-2 p-3">Demirbaş</UButton>
      </div>

    </div>
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

.emlak_detaylar {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 5fr));
  margin: 0rem 6rem;
}

.mt_kare, .oda_sayisi, .bina_yasi, .bulundugu_kat, .kat_sayisi, .isitma, .balkon, .asansor, .otopark, .esya, .aidat{
  border: 1px solid rgb(var(--color-gray-200) / 1);
  margin:1rem;
  padding:1rem; 
}
</style>
