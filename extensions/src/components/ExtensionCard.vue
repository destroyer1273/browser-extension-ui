<script setup>
import { ref, computed } from "vue";
const props = defineProps({
    id: Number,
    name: String,
    logoUrl: String,
    description: String,
    isActive: Boolean,
});

const emit = defineEmits(['toggle-change']);

const handleToggle = () => {
    
}

const toggleId = computed(() => {
    const baseId = `toggle-${props.name.toLowerCase().replace(/\s+/g, '-')}`;
    return baseId;
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
            <input class="toggle" type="checkbox" role="switch" :id="toggleId" :checked="props.isActive" @change="handleToggle"> <!-- :checked="props.isActive" -->
            <label class="label-switch" :for="toggleId">Toggle</label>
        </div>
   </div>
</template>

<style>
    * {
        padding: 0;
        margin: 0;
        box-sizing: border-box;
    }
    /* TOGGLE TOGGLE TOGGLE */
    
</style>
