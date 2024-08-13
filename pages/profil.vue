<template>
    <p class="text-2xl px-4 py-4 pb-2 bg-lime">Hesap Özeti | Bireysel Hesap</p>
    <hr />
    <div class="grid grid-cols-1 md:grid-cols-3 gap-4 mt-4 mb-8 ">
        <div class="my-box-shadow bg-white shadow p-4 rounded-lg">
            <div class="flex items-center justify-between mb-2">
                <i class="fa-solid fa-file-alt text-8xl ml-4"></i>
                <div class="ml-6 text-right">
                    <p class="text-gray-600">Yayında olan ilan adedi</p>
                    <p class="text-6xl font-semibold">0</p>
                </div>
            </div>
        </div>
        <div class="my-box-shadow bg-white shadow p-4 rounded-lg">
            <div class="flex items-center justify-between mb-2">
                <i class="fa-regular fa-star text-8xl ml-4"></i>
                <div class="ml-4 text-right">
                    <p class="text-gray-600">Yayında olan ilan adedi</p>
                    <p class="text-6xl font-semibold">0</p>
                </div>
            </div>
        </div>
        <div class="my-box-shadow bg-white shadow p-4 rounded-lg">
            <div class="flex items-center justify-between mb-2">
                <i class="fa-regular fa-hourglass-half text-8xl ml-4"></i>
                <div class="ml-6 text-right">
                    <p class="text-gray-600">Süresi bitmiş ilanlarım</p>
                    <p class="text-6xl font-semibold">0</p>
                </div>
            </div>
        </div>
    </div>

    <div class="my-box-shadow bg-white shadow p-4 rounded-lg mb-8">
        <h2 class="text-lg font-semibold mb-2">Hemen İlan Ver</h2>
        <p class="text-gray-600">Siz de adapazari.com'a ilan verin, Lorem ipsum dolor sit, amet consectetur adipisicing
            elit. Tenetur tempore sint modi! Lorem ipsum dolor sit amet. Lorem, ipsum dolor.</p>
        <a href="#" class="text-blue-500 block text-right">İlan Vermek İstiyorum</a>
    </div>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
        <div class="bg-white my-box-shadow shadow p-4 rounded-lg">
            <h2 class="text-lg font-semibold mb-2">Fiyatı Düşen Favoriler</h2>
            <p class="text-gray-600">Fiyatı düşen favorilerinizdeki ürünleri burada görüntüleyebilirsiniz Lorem ipsum
                dolor sit amet..</p>
        </div>
        <div class="my-box-shadow bg-white shadow p-4 rounded-lg">
            <h2 class="text-lg font-semibold mb-2">Destek Taleplerim</h2>
            <p class="text-gray-600">Cevaplanmış destek talepleriniz buradadır Lorem ipsum dolor sit amet consectetur
                adipisicing elit. Natus, ex? Lorem ipsum.</p>
        </div>
    </div>


</template>
<script setup lang="ts">
definePageMeta({
    layout: 'profil-ve-detaylari'
});
</script>
<style scoped>
.grid>div {
    position: relative;
    /* Konumlandırma için gerekli */
}

/* Ok işareti */
.grid>div::before {
    content: '';
    /* İçerik boş */
    position: absolute;
    /* Mutlak konumlandırma */
    top: -12px;
    /* Üstten uzaklık */
    left: -12px;
    /* Soldan uzaklık */
    width: 0;
    height: 0;
    border-left: 12px solid transparent;
    /* Sağ üst köşe ok */
    border-right: 12px solid transparent;
    /* Sağ üst köşe ok */
    border-bottom: 12px solid #3f475f;
    /* Alt kenar siyah renk */
    border-top: 12px solid transparent;
    /* Üst kenar şeffaf */
    transform: rotate(-45deg);
    /* Okun doğru açıda görünmesi için döndür */
}

/* styles.css */
.my-box-shadow {
    box-shadow: rgba(0, 0, 0, 0.15) 0px 5px 15px 0px;
    transition: box-shadow 0.3s ease-in-out;
    /* Geçiş efekti */
}

.my-box-shadow:hover {
    box-shadow: rgba(0, 0, 0, 0.2) 0px 12px 28px 0px, rgba(0, 0, 0, 0.1) 0px 2px 4px 0px, rgba(255, 255, 255, 0.05) 0px 0px 0px 1px inset;
}
</style>