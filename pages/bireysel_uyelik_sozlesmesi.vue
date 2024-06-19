<template>
    <div class="content">
        <div class="content__menu">
            <!-- <h2 class="content__menu-title">Biz</h2> -->
            <ul class="content__menu-list">
                <li class="content__menu-item">
                    <router-link to="/hakkimizda" class="content__menu-link">Bireysel Üyelik Sözleşmesi</router-link>
                </li>
                <li class="content__menu-item">
                    <router-link to="/iletisim" class="content__menu-link">
                        İlan Kuralları</router-link>
                </li>
                <li class="content__menu-item">
                    <router-link to="/sikca-sorulan-sorular" class="content__menu-link">
                        Gizlilik Kuralları</router-link>
                </li>
                <li class="content__menu-item">
                    <router-link to="/sikca-sorulan-sorular" class="content__menu-link">
                        Yardım</router-link>
                </li>
            </ul>
        </div>
        <div class="biz_icerik">

            <div class="rounded-lg">
                <p class="text-2xl px-4 py-6 bg-lime">Bireysel Üyelik Sözleşmesi</p>
                <p class="text-lg px-4 py-1 bg-lime">
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Rerum laboriosam impedit quaerat beatae
                    molestias incidunt
                    <br /><br />
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Rerum laboriosam impedit quaerat beatae
                    molestias incidunt
                    perspiciatis natus placeat nemo corporis vero dolorum corrupti nobis ullam obcaecati esse eaque,
                    neque
                    sint
                    voluptatem tempore id earum adipisci ex? Magni suscipit alias, ipsa odit distinctio tenetur
                    voluptate
                    facere
                    voluptas, repellat natus consectetur eum corporis modi atque. Dolor aut odio, natus officia eius
                    nemo,
                    perspiciatis
                    consequatur minima voluptates eos illum ipsam aliquam, quod id iste. Natus neque nesciunt, quibusdam
                    quaerat dolorem
                    accusantium corporis assumenda reiciendis repellat aperiam aliquid vero! Possimus vitae nesciunt
                    dolor
                    quas eos
                    aliquid, iure ipsam officia autem neque expedita omnis voluptatibus obcaecati eaque! Facilis a,
                    maiores
                    repellat
                    quasi nemo similique commodi. Vel repudiandae a autem minus impedit. Harum accusamus et recusandae
                    ipsa
                    suscipit
                    pariatur, libero inventore perspiciatis obcaecati odio porro magni commodi dolorem cumque totam
                    provident iusto
                    explicabo ad iure eaque eius. Molestiae repellat expedita sint quasi tempora ullam asperiores et
                    quia
                    laudantium
                    ducimus reprehenderit temporibus voluptas ex accusantium veniam, numquam laboriosam. Fugit possimus
                    ex
                    sapiente
                    temporibus optio reiciendis sequi, corporis voluptas illum quaerat autem atque aliquam perspiciatis
                    dolores enim,
                    omnis quidem sit.
                    <br /><br />
                    Quam enim eius, sed numquam cumque vero inventore et quibusdam excepturi ipsam. Quasi,
                    consectetur
                    sit. Ad eum molestiae maxime odio nihil. Aut vel tenetur, mollitia eos deserunt, beatae non fuga
                    eligendi natus,
                    animi quibusdam voluptatem recusandae. Incidunt ratione praesentium molestiae magni et cumque illum
                    harum nihil rem
                    quaerat similique nesciunt aliquam nostrum possimus, obcaecati hic atque dolore, voluptas deserunt
                    quam
                    quae modi
                    sapiente. Reprehenderit esse consectetur deserunt recusandae dolor enim explicabo est repellat iste
                    molestias error
                    beatae nam, mollitia sint, ea eius autem at harum possimus? Suscipit illum ducimus qui aliquam
                    placeat
                    obcaecati
                    quas provident id, quidem cupiditate eaque explicabo labore aperiam nemo at reprehenderit libero
                    praesentium
                    deleniti nostrum beatae corporis. Reiciendis necessitatibus quod, nulla at placeat corrupti.
                </p>
            </div>
        </div>
    </div>
    <myFooter />
</template>
<script>
import myFooter from '~/pages/myFooter.vue'; // Header bileşenini içeri aktar
export default {
    components: {
        myFooter // Footer bileşenini kullanılabilir hale getir
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
    border-bottom: 2px solid #fff;
    background-color: #fff;
    margin-bottom: 0.2rem;
    padding: 1rem;
}

.content__menu-link {
    /* kategorilerdeki link ayarları */
    color: #333;
    text-decoration: none;
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
        margin:0.5rem;
        padding:0.5rem 0.5rem 2rem 0.5rem;
        margin-top: 1rem;
        margin-bottom:3rem;
        border-radius: 0.3rem;
    }
}
</style>