<script setup lang="ts">
import { PropType } from 'vue';
import Job from '@/types/Job';
    const props = defineProps({
        jobs: {
            type: Array as PropType<Job[]>,
            required: true
        }
    })
</script>

<template>
    <div>
        <ul>
            <li class="bg-blue-950 text-white font-semi-bold rounded-md" v-for="job in jobs" :key="job.id">{{ job.title }} in {{ job.location }}
            <div class="salary">{{ job.salary }}</div>
            <div class="description">
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Architecto velit in eaque!</p>
            </div>
            </li>
        </ul>
    </div>
    <!-- {{ jobs  }} -->
</template>

<style scoped>

</style>
