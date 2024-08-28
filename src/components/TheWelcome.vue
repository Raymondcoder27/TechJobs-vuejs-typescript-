<script setup lang="ts">
    const props = defineProps{
        type: string,
        required: true,
    }
</script>

<template>
    <div class="justify-center text-center mx-auto my-4">
        <h3 class="text-gray-500">Welcome {{ name }}</h3>
    </div>
</template>