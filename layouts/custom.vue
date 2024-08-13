<template>
    <HeaderComponent />
    <div class="content">
        <div class="content__menu">
            <!-- <h2 class="content__menu-title">Biz</h2> -->
            <ul class="content__menu-list">
                <li class="content__menu-item">
                    <router-link to="/hakkimizda" class="content__menu-link">Hakkımızda</router-link>
                </li>
                <li class="content__menu-item">
                    <router-link to="/iletisim" class="content__menu-link">
                        İletişim</router-link>
                </li>
                <li class="content__menu-item">
                    <router-link to="/sikca_sorulan_sorular" class="content__menu-link">Sıkça Sorulan
                        Sorular</router-link>
                </li>
                <li class="content__menu-item">
                    <router-link to="/site_haritasi" class="content__menu-link">Site Haritası</router-link>
                </li>
            </ul>
        </div>
        <div class="biz_icerik">
            <router-view></router-view>
        </div>
    </div>
    <myFooter />
</template>
<script>
import HeaderComponent from '~/layouts/default.vue'; // default.vue dosyasını import edip header bileşenini çağırdık
import myFooter from '~/pages/myFooter.vue'; //footeri çağırdık
export default {
    components: {
        HeaderComponent, myFooter
    },
    mounted() {
        this.setupMenuListeners();
    }, methods: {
        setupMenuListeners() {
            const menuItems = document.querySelectorAll('.content__menu-item'); menuItems.forEach(item => {
                item.addEventListener('click', function () {
                    // Aktif olan öğenin sınıfını kaldır
                    menuItems.forEach(el => el.classList.remove('active'));

                    // Tıklanan öğeye aktif sınıfını ekle
                    this.classList.add('active');
                });
            });
        }
    }

}
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
}

.content__menu-item.active {
    background-color: #e0e0e0;
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

.biz_icerik {
    flex: 7;
    box-shadow: rgba(0, 0, 0, 0.1) 0px 14px 28px, rgba(0, 0, 0, 0.22) 0px 10px 10px;
    padding: 1rem 2rem 2rem 2rem;
    margin-top: 2rem;
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

    .biz_icerik {
        margin: 0.5rem;
        padding: 0.5rem 0.5rem 2rem 0.5rem;
        margin-top: 1rem;
        margin-bottom: 3rem;
        border-radius: 0.3rem;
    }
}
</style>