<template>
<div class="grid-container">
        <div class="grid-item">1</div>
        <div class="grid-item">2</div>
        <div class="grid-item">3</div>
        <div class="grid-item">4</div>
        <div class="grid-item">5</div>
        <div class="grid-item">6</div>
        <div class="grid-item">7</div>
    </div>
</template>

<style>

.grid-container {
    display: grid;
    grid-template-columns: repeat(7, 1fr);
}

.grid-item {
    background-color: #4CAF50;
    color: white;
    padding: 20px;
    text-align: center;
    border: 1px solid #ddd;
}

.grid-item-span {
    grid-column: span 7;
    background-color: #2196F3;
}

</style>