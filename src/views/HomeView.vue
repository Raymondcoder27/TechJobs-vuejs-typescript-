<script setup lang="ts">
import {reactive, ref, toRefs} from 'vue'
// import AppHeader from '@/components/AppHeader.vue';
  
// import TheWelcome from '../components/TheWelcome.vue'
import JobList from '@/components/JobList.vue';
import Job from '@/types/Job';
import OrderTerm from '@/types/OrderTerm';

const order = ref<OrderTerm>('title')

const handleClick = (term: OrderTerm) =>{
  order.value = term
}


const jobs = ref<Job[]>([
  {title: 'CTO',
  location: 'Kasese',
  salary: 'USD 8,000',
  id: '1'
},
{title: 'Vue JS Frontend Dev',
  location: 'Wakiso',
  salary: 'USD 5,000',
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

        <div class="w-full text-gray-500 block mx-auto items-center justify-center">
          <button
          @click="handleClick('title')" class="bg-gray-200 font-semibold text-black p-1 rounded-md mr-2 cursor-pointer">
            Order By Title
          </button>
          <button
          @click="handleClick('salary')" class="bg-gray-200 font-semibold text-black p-1 rounded-md mr-2 cursor-pointer">
            Order By Salary
          </button>
          <button
          @click="handleClick('location')" class="bg-gray-200 font-semibold text-black p-1 rounded-md mr-2 cursor-pointer">
            Order By Location
          </button>
         <JobList :jobs="jobs" :order="order" />
        </div>
    </div>
</template>
