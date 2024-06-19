<template>
    <div class="container">
        <div class="i2">
            <div class="aa"></div>
            <div class="bb"></div>
        </div>
        <div class="deneme"></div>
    </div>

</template>
<style scoped>
.container {
    border:2px solid black;
    height:5rem;
    width:5rem;
    display: grid;
    grid-auto-columns: 1fr;
    grid-auto-rows: 1fr;
    gap: 0% 1px;
    grid-auto-flow: row;
}

.i2 {    border:2px solid black;
    height:5rem;
    width:5rem;
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 1fr;
    gap: 0px 0px;
    grid-auto-flow: row;
    grid-template-areas:
        "aa bb";
}

.aa {    border:2px solid black;
    height:5rem;
    width:5rem;
    grid-area: aa;
}

.bb {    border:2px solid black;
    height:5rem;
    width:5rem;
    grid-area: bb;
}

.deneme {    border:2px solid black;
    height:5rem;
    width:5rem;
    grid-area: 1 / 1 / 2 / 2;
}
</style>