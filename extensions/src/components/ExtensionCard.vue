<script setup>
import { ref, computed } from "vue";
const props = defineProps({
    id: Number,
    name: String,
    logoUrl: String,
    description: String,
    isActive: Boolean,
});

const emit = defineEmits(['toggle-change', 'remove-card']);

const changeToggle = () => {
    emit('toggle-change', (props.id));
    console.log("Extension id", props.id);
}

const toggleId = computed(() => {
    const baseId = `toggle-${props.name.toLowerCase().replace(/\s+/g, '-')}`;
    return baseId;
});

const removeCard = () => {
    emit('remove-card', (props.id));
    console.log(props.id);
}
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
            <button @click="removeCard">Remove</button>
            <input class="toggle" type="checkbox" role="switch" :id="toggleId" :checked="props.isActive" @change="changeToggle"> <!-- :checked="props.isActive" -->
            <label class="label-switch" :for="toggleId" @click="handleToggle">Toggle</label>
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
