<template>
    <p class="text-2xl px-4 py-4 pb-2 bg-lime">Şifre Değişikliği</p>
    <hr />
    <div class="max-w-4xl mx-auto bg-white shadow-md rounded-lg p-6 mt-10">
        <div class="grid grid-cols-1 md:grid-cols-1 gap-4">
            <!-- Sol Sütun -->
            <div>
                <p>Şifrenizi değiştirmek için mevcut ve yeni şifrenizi girin.</p>
                <div class="grid items-center mt-8 pb-2">
                    <div class="flex items-center m-4 border-b border-gray-300 pb-2">
                        <label class="block text-gray-700 font-semibold mr-4">Mevcut Şifre:</label>
                        <!-- <p class="text-gray-900">cgurhan36</p> -->
                        <UInput type="password" v-model="mevcutSifre" class="ml-8"/>
                    </div>
                    <div class="flex items-center m-4 border-b border-gray-300 pb-2">
                        <label class="block text-gray-700 font-semibold mr-4">Yeni Şifre:</label>
                        <!-- <p class="text-gray-900">cgurhan36</p> -->
                        <UInput type="password" v-model="mevcutSifre" class="ml-14"/>
                    </div>
                    <div class="flex items-center m-4 border-b border-gray-300 pb-2">
                        <label class="block text-gray-700 font-semibold mr-4">Yeni Şifre Tekrar:</label>
                        <!-- <p class="text-gray-900">cgurhan36</p> -->
                        <UInput type="password" v-model="mevcutSifre" class="ml-2"/>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <div class="flex justify-center md:justify-end">
        <button class="bg-blue-500 text-white mt-4 px-16 py-2 rounded hover:bg-blue-600">Düzenle</button>
    </div>
</template>
<script setup lang="ts">
definePageMeta({
    layout: 'profil-ve-detaylari'
});
const mevcutSifre = ref('');
const yeniSifre = ref('');
const yeniSifreTekrar = ref('');
</script>
<style></style>