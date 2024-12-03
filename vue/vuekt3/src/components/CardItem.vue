<script setup>
    const props = defineProps({
        id: Number,
        name: String,
        image: String
    })
</script>

<template>
    <div class="card">
        <img class="card-image" :src="image" alt="Image" width="300" height="300"/>
        <h2 class="card-title">{{ id }} - {{ name }}</h2>
    </div>
</template>

<style scoped>
.card {
    border: 1px solid #ccc;
    padding: 20px;
    text-align: center;
    border-radius: 8px;
    background-color: #f9f9f9;
}

.card-image {
    border-radius: 4px;
}

.card-title {
    font-size: 1.5rem;
    color: #333;
}
</style>
