<script setup>
const props = defineProps({
    countArray: Array,
    page: Number
});

const emit = defineEmits(['changePage']);

function changePage(num) {
    emit('changePage', num);
}
</script>

<template>
    <div class="btns-container">
        <button 
            @click="changePage(page - 1)" 
            :disabled="page <= 1" 
            class="nav-btn">
            {{ '<--' }}
        </button>
        
        <button 
            v-for="numb in countArray" 
            :key="numb" 
            @click="changePage(numb)" 
            :class="['btn', numb === page && 'active']">
            {{ numb }}
        </button>
        
        <button 
            @click="changePage(page + 1)" 
            :disabled="page === countArray.length" 
            class="nav-btn">
            {{ '-->' }}
        </button>
    </div>
</template>

<style scoped>
    .btns-container {
        display: flex;
        gap: 8px;
        justify-content: center;
        margin: 15px;
    }
    
    .btn, .nav-btn {
        padding: 8px 16px;
        cursor: pointer;
        border: 1px solid #ccc;
        border-radius: 4px;
        background-color: #f9f9f9;
        transition: background-color 0.3s;
    }

    .btn:hover, .nav-btn:hover {
        background-color: #f0f0f0;
    }

    .active {
        font-weight: bold;
        background-color: #007bff;
        color: white;
    }

    .nav-btn:disabled {
        background-color: #d3d3d3;
        cursor: not-allowed;
    }
</style>
