<script setup lang="ts">
import { PropType } from 'vue';
import Job from '@/types/Job';
import type OrderTerm from '@/types/OrderTerm';
    const props = defineProps({
        jobs: {
            type: Array as PropType<Job[]>,
            required: true
        },
        order: {
            required: true,
            type: String as PropType<OrderTerm>
        }
    })
</script>

<template>
    <div>
        <ul>
           ordered by {{ order }}
            <li class="bg-blue-950 text-white font-semibold rounded-md mx-auto w-[600px] py-2 my-5" v-for="job in jobs" :key="job.id">{{ job.title }} in {{ job.location }}
            <div class="salary">{{ job.salary }}</div>
            <div class="text-sm text-gray-200 font-thin">
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Architecto velit in eaque!</p>
            </div>
            </li>
        </ul>
    </div>
    <!-- {{ jobs  }} -->
</template>

<style scoped>

</style>
