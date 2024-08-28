<script setup lang="ts">
import { PropType, computed } from 'vue';
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

    const orderedJobs = computed(()=>{
        return [...props.jobs].sort((a: Job, b: Job)=> {
            return a[props.order] > b[props.order] ? 1 : -1
        })
    })
</script>

<template>
    <div>
        <transition-group tag="ul" name="list">
           ordered by {{ order }}
            <li class="bg-blue-950 text-white font-semibold rounded-md mx-auto w-[600px] py-2 my-5" v-for="job in orderedJobs" :key="job.id">
                <h2>{{ job.title }} in {{ job.location }}</h2>
            <div class="salary">{{ job.salary }}</div>
            <div class="text-sm text-gray-200 font-thin">
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Architecto velit in eaque!</p>
            </div>
            </li>
        </transition-group>
    </div>
    <!-- {{ jobs  }} -->
</template>

<style scoped>
    .list-move{
        transition: all 1s
    }
</style>
