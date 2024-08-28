<script setup lang="ts">
import {reactive, ref, toRefs} from 'vue'
// import AppHeader from '@/components/AppHeader.vue';
// import TheWelcome from '../components/TheWelcome.vue'
import JobList from '@/components/JobList.vue';
import Job from '@/types/Job.vue';


const jobs = ref<Job[]>([
  {title: 'CTO',
  location: 'Kasese',
  salary: 'USD 10,000',
  id: '1'
},
{title: 'Vue JS Frontend Dev',
  location: 'Wakiso',
  salary: 'USD 6,000',
  id: '2'
},{title: 'Golang Backend Dev',
  location: 'Nansana',
  salary: 'USD 6,000',
  id: '3'
},
])


// return { ...toRefs(state), name, age, changeName}
 

</script>

<template>
  <!-- <main>
    <TheWelcome :name="name" />
  </main> -->
  <div class="justify-center text-center mx-auto my-4">

        <div class="w-full text-gray-500 block">
         <JobList :jobs="jobs" />
        </div>
    </div>
</template>
