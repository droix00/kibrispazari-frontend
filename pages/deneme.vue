<template>
    <div class="main-content">
        <aside>
            <nav>
                <ul>
                    <li><a href="#" @click.prevent="setActive('emlak')">AA</a></li>
                    <li><a href="#" @click.prevent="setActive('araba')">BB</a></li>
                    <li><a href="#" @click.prevent="setActive('elektronik')">CC</a></li>
                </ul>
            </nav>
        </aside>
        <main>
            <div v-if="active === 'emlak'">A</div>
            <div v-if="active === 'araba'">B</div>
            <div v-if="active === 'elektronik'">C</div>
        </main>
    </div>
</template>

<script>
export default {
    data() {
        return {
            active: 'araba' // Sayfa açıldığında ilk gösterilecek içerik
        }
    },
    methods: {
        setActive(menu) {
            this.active = menu;
        }
    }
}
</script>

<style>
.main-content {
    display: flex;
    height: 100%;
}

aside {
    width: 200px;
    background: #f4f4f4;
    padding: 10px;
}

main {
    flex: 1;
    padding: 10px;
}
</style>