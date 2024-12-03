<script setup>
import CardItem from './CardItem.vue';

const props = defineProps({
    recipes: Array
});
</script>

<template>
    <div class="card-container">
        <CardItem 
            v-for="card in recipes"
            :key="card.id"
            :name="card.name"
            :image="card.image"
            :id="card.id"
        />
    </div>
</template>

<style scoped>
.card-container {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 20px;
    justify-items: center;
    padding: 20px;
}

@media (max-width: 768px) {
    .card-container {
        grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    }
}
</style>
