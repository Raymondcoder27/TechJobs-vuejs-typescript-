<script setup lang="ts">
import {reactive, ref, toRefs} from 'vue'
// import AppHeader from '@/components/AppHeader.vue';
// import TheWelcome from '../components/TheWelcome.vue'

const name = ref<string>("Raymond")
const age = ref<Number>(45)

const state = reactive({
  name: "John",
  age: 25 as string | number
})



const changeName = () => {
  if (name.value == "Raymond"){
    name.value = "Mwebe"
    age.value = 54
  }else if(name.value== "Mwebe"){
    name.value = "Raymond"
    age.value = 45
  }
}
// return { ...toRefs(state), name, age, changeName}
 

</script>

<template>
  <!-- <main>
    <TheWelcome :name="name" />
  </main> -->
  <div class="justify-center text-center mx-auto my-4">
        <h3 class="text-gray-500">Welcome, {{ name }}, age {{ age }}</h3>
        <button class="bg-black text-white rounded-md p-1 text-sm font-semi-bold hover:bg-gray-300 hover:text-black hover:font-semibold"
        @click="changeName">
          Change Name
        </button>

        <div class="w-full text-gray-500 block">
          <h3>Reactive</h3>
         Age is {{ state.age }} and  name is {{ state.name }}
        </div>
    </div>
</template>
