<template>
    <NuxtLink :to="urlToRedirect" 
        class="self-end bg-[#11b0c8] gap-2 flex py-[6px] px-1 rounded-[32px] text-sm items-center mt-auto"
        target="_blanck"
        >
        <Info/>
        Saiba Mais
    </NuxtLink>
</template>

<script setup>
import Info from '../Icons/info.vue';

const props = defineProps({
    id: Number,
    type: {
        type: String,
        default: "character",
    }
})

const urlToRedirect = computed(() => {
    if(props.type === 'character') {
        return `/character/${props.id}`
    }
    return `/episode/${id}`
});
</script>