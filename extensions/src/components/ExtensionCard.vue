<script setup>
import { ref } from "vue";

const props = defineProps({
    name: String,
    logoUrl: String,
    description: String,
    isActive: Boolean,
});


</script>

<template>
   <div class="card">
        <div class="card-top">
            <img :src="props.logoUrl" class="logo" alt="Logo">
            <div>
                <h4 class="card-name">{{ props.name }}</h4>
                <p class="card-descr">{{ props.description }}</p>
            </div>
        </div>
        <div class="card-bottom">
            <button>Remove</button>
            <input type="checkbox" role="switch">
        </div>
   </div>
</template>

<style scoped>
    .card {
        box-sizing: border-box;
        border: 0.6px #575656 solid;
        border-radius: 15px;
        width: 330px;
        background-color: #292941;
        padding: 12px 6px;
        flex-shrink: 0;
    }
    .card-top {
        display: flex;
        flex-direction: row;
    }
</style>
