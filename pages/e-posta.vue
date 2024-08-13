<template>
    <p class="text-2xl px-4 py-4 pb-2 bg-lime">E-posta</p>
    <hr />
    <div class="max-w-4xl mx-auto bg-white shadow-md rounded-lg p-6 mt-10">
        <div class="grid grid-cols-1 md:grid-cols-1 gap-4">
            <!-- Sol Sütun -->
            <div>
                <p>E-posta adresiniz, yayınlanmasını istediğiniz ilanlarınızda ve diğer kullanıcılara göndereceğiniz
                    mesajlarda gösterilecektir.</p>
                <div class="flex items-center mt-8 pb-2">
                    <label class="block text-gray-700 font-semibold mr-4">Kayıtlı e-posta adresiniz:</label>
                    <UInput v-model="ePosta" class="ml-3" disabled />
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
const ePosta = ref('civang@gmail.com');
</script>
<style></style>