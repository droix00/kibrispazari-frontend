<template>
    <p class="text-2xl px-4 py-4 pb-2 bg-lime">Kişisel Bilgilerim</p>
    <hr />
    <div class="max-w-4xl mx-auto bg-white shadow-md rounded-lg p-6 mt-10">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
            <!-- Sol Sütun -->
            <div>
                <div class="flex items-center m-4 border-b border-gray-300 pb-2">
                    <label class="block text-gray-700 font-semibold mr-4">Kullanıcı Adı:</label>
                    <!-- <p class="text-gray-900">cgurhan36</p> -->
                    <UInput v-model="kullaniciAdi" class="ml-1" disabled />
                </div>
                <div class="m-4 border-b border-gray-300 pb-2">
                    <div class="flex items-center">
                        <label class="block text-gray-700 font-semibold mr-4">Ad Soyad:</label>
                        <UInput v-model="adiSoyadi" class="ml-6" disabled />
                    </div>
                    <div class="block mt-1">
                        <span class="text-gray-600 text-sm">(Nasıl görünür: <span class="font-medium ml-2">{{
                            nasilGorunur }}</span>)</span>
                    </div>
                </div>
                <div class="flex items-center m-4 border-b border-gray-300 pb-2">
                    <label class="block text-gray-700 font-semibold mr-4">Cinsiyet:</label>
                    <USelectMenu v-model="cinsiyet" :options="cinsiyetSec" class="ml-10" disabled />
                </div>
                <div class="flex items-center m-4 border-b border-gray-300 pb-2">
                    <label class="block text-gray-700 font-semibold mr-4">Ev Telefonu:</label>
                    <UInput v-model="evTelefonu" class="ml-3" disabled />
                </div>
                <div class="flex items-center m-4 border-b border-gray-300 pb-2">
                    <label class="block text-gray-700 font-semibold mr-4">İş Telefonu:</label>
                    <UInput v-model="isTelefonu" class="ml-4" disabled />
                </div>
            </div>
            <!-- Sağ Sütun -->
            <div class="flex flex-col items-center justify-center">
                <div
                    class="w-32 h-32 border border-gray-300 rounded-full flex items-center justify-center cursor-pointer mb-4">
                    <span class="text-blue-500 font-bold">Fotoğraf Ekle</span>
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
const kullaniciAdi = ref('cgurhan985');
const adiSoyadi = ref('Civan Gürhan');
const nasilGorunur = ref('Civan G.');
const cinsiyetSec = ['Erkek', 'Kadın',];
const cinsiyet = ref(cinsiyetSec[0]);
const evTelefonu = ref('-');
const isTelefonu = ref('-');
</script>
<style></style>