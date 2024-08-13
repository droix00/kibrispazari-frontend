<template>
    <HeaderComponent />
    <div class="content">
        <div class="content__menu">
            <ul class="content__menu-list">
                <li class="content__menu-item">
                    <router-link to="profil" class="content__menu-link">Hesap Özeti</router-link>
                </li>
                <li class="content__menu-item">
                    <router-link @click="toggleHesapBilgilerim" to="#" class="content__menu-link">Hesap Bilgilerim
                        <i class="fa-solid fa-caret-down"></i>
                    </router-link>
                    <ul v-if="isHesapBilgilerimOpen" class="dropdown-menu">
                        <li><router-link to="/kisisel-bilgilerim">Kişisel Bilgilerim</router-link></li>
                        <li><router-link to="/cep-telefonu">Cep Telefonu</router-link></li>
                        <li><router-link to="/e-posta">E-posta</router-link></li>
                        <li><router-link to="/sifre-degisikligi">Şifre Değişikliği</router-link></li>
                    </ul>
                </li>
                <li class="content__menu-item">
                    <router-link @click="toggleIlanYonetimi" to="#" class="content__menu-link">İlan Yönetimi
                        <i class="fa-solid fa-caret-down"></i>
                    </router-link>
                    <ul v-if="isIlanYonetimiOpen" class="dropdown-menu">
                        <li><router-link to="yayindaki-ilanlarim">Yayındaki ilanlarım</router-link></li>
                        <li><router-link to="#">Onay bekleyen ilanlarım</router-link></li>
                        <li><router-link to="#">Süresi bitmiş ilanlarım</router-link></li>
                    </ul>
                </li>
                <li class="content__menu-item">
                    <router-link to="#" class="content__menu-link">Bildirimlerim</router-link>
                </li>
                <li class="content__menu-item">
                    <router-link to="#" class="content__menu-link">Favori İlanlarım</router-link>
                </li>
                <li class="content__menu-item">
                    <router-link @click="toggleIzinlerim" to="#" class="content__menu-link">İzinlerim
                        <i class="fa-solid fa-caret-down"></i>
                    </router-link>
                    <ul v-if="isIzinlerimOpen" class="dropdown-menu">
                        <li><router-link to="#">Bildirim Tercihleri</router-link></li>
                        <li><router-link to="#">E-posta Aboneliği</router-link></li>
                    </ul>
                </li>
                <li class="content__menu-item">
                    <router-link to="#" class="content__menu-link">Destek Taleplerim</router-link>
                </li>
                <li class="content__menu-item">
                    <router-link to="#" class="content__menu-link">Çıkış Yap</router-link>
                </li>
            </ul>
        </div>
        <div class="profil_icerik">
            <router-view></router-view>
        </div>
    </div>
    <myFooter />
</template>

<script>
import HeaderComponent from '~/layouts/default.vue';
import myFooter from '~/pages/myFooter.vue';

export default {
    components: {
        HeaderComponent, myFooter
    },
    mounted() {
        this.setupMenuListeners();
    },
    data() {
        return {
            isHesapBilgilerimOpen: false,
            isIlanYonetimiOpen: false,
            isIzinlerimOpen: false
        };
    },
    methods: {
        setupMenuListeners() {
            const menuItems = document.querySelectorAll('.content__menu-item'); menuItems.forEach(item => {
                item.addEventListener('click', function () {
                    // Aktif olan öğenin sınıfını kaldır
                    menuItems.forEach(el => el.classList.remove('active'));

                    // Tıklanan öğeye aktif sınıfını ekle
                    this.classList.add('active');

                });
            });
        }, 
        toggleHesapBilgilerim() {
            this.isHesapBilgilerimOpen = !this.isHesapBilgilerimOpen;
            this.isIlanYonetimiOpen = false;  // Diğer dropdown'ları kapat
            this.isIzinlerimOpen = false;
        },
        toggleIlanYonetimi() {
            this.isIlanYonetimiOpen = !this.isIlanYonetimiOpen;
            this.isHesapBilgilerimOpen = false;  // Diğer dropdown'ları kapat
            this.isIzinlerimOpen = false;
        },
        toggleIzinlerim() {
            this.isIzinlerimOpen = !this.isIzinlerimOpen;
            this.isHesapBilgilerimOpen = false;  // Diğer dropdown'ları kapat
            this.isIlanYonetimiOpen = false;
        }
    }
}

// ORİJİNAL


// import HeaderComponent from '~/layouts/default.vue';
// import myFooter from '~/pages/myFooter.vue';

// export default {
//     components: {
//         HeaderComponent, myFooter
//     },
//     data() {
//         return {
//             isHesapBilgilerimOpen: false,
//             isIlanYonetimiOpen: false,
//             isIzinlerimOpen: false
//         };
//     },
//     methods: {
//         toggleHesapBilgilerim() {
//             this.isHesapBilgilerimOpen = !this.isHesapBilgilerimOpen;
//             this.isIlanYonetimiOpen = false;  // Diğer dropdown'ları kapat
//             this.isIzinlerimOpen = false;
//         },
//         toggleIlanYonetimi() {
//             this.isIlanYonetimiOpen = !this.isIlanYonetimiOpen;
//             this.isHesapBilgilerimOpen = false;  // Diğer dropdown'ları kapat
//             this.isIzinlerimOpen = false;
//         },
//         toggleIzinlerim() {
//             this.isIzinlerimOpen = !this.isIzinlerimOpen;
//             this.isHesapBilgilerimOpen = false;  // Diğer dropdown'ları kapat
//             this.isIlanYonetimiOpen = false;
//         }
//     }
// }
</script>

<style scoped>
.content {
    /*Content alanı */
    display: flex;
    margin: 0rem 12.2rem 2rem 12.8rem;
}

.content__menu {
    /*contentteki sol menü kategoriler ve alt başlıkları */
    flex: 2;
    padding: 2rem 1rem 1rem 0rem;
}

.content__menu-list {
    /*alt kategoriler */
    box-shadow: rgba(0, 0, 0, 0.1) 0px 14px 28px, rgba(0, 0, 0, 0.22) 0px 10px 10px;
    list-style-type: none;
    background-color: #f0f0f0;
    padding: 1rem;
}

.content__menu-item {
    /* her alt kategori için bottom ayarlandı */
    background-color: #fff;
    margin-bottom: 0.2rem;
}

.content__menu-item:hover {
    background-color: #e0e0e0;
    /* Üzerine gelindiğinde ana menü arka plan rengi */
}

.content__menu-item.active {
    background-color: #e0e0e0;
    /* Seçili başlığın arkaplan rengi */
}

.content__menu-link {
    /* kategorilerdeki link ayarları */
    color: #333;
    text-decoration: none;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem;
}

.profil_icerik {
    flex: 7;
    height: 100%;
    box-shadow: rgba(0, 0, 0, 0.1) 0px 14px 28px, rgba(0, 0, 0, 0.22) 0px 10px 10px;
    padding: 1rem 2rem 2rem 2rem;
    margin-top: 2rem;
    max-height: auto;
}

.dropdown-menu {
    /* açılır menü için stil */
    position: relative;
    background-color: #f9f9f9;
    z-index: 10;
}

.dropdown-menu li {
    padding: 0.5rem 1.4rem;
    font-size: 0.9rem;
    border-bottom: 1px solid #e0e0e0;
    
    display: grid;
}

.dropdown-menu li:hover {
    background-color: #e0e0e05e;
    /* Üzerine gelindiğinde ana menü arka plan rengi */
}

@media all and (max-width:768px) {
    .content {
        /*Content alanı */
        display: flex;
        margin: 0;
    }

    .content__menu {
        display: none;
    }

    .content__menu {
        padding: 1rem;
        margin-bottom: 1rem;
        justify-content: center;
        align-items: center;
    }

    .profil_icerik {
        margin: 0.5rem;
        padding: 0.5rem 0.5rem 2rem 0.5rem;
        margin-top: 1rem;
        margin-bottom: 3rem;
        border-radius: 0.3rem;
    }
}
</style>
