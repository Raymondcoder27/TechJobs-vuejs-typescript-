<script setup lang="ts">
import {ref, type Ref} from "vue";
import {useRoute} from "vue-router";
import router from "@/router";
import Home from "vue-material-design-icons/Home.vue"

const route = useRoute()

type SideMenuLink ={
  name:string
  label:string
}

const sideMenu:Ref<Array<SideMenuLink>> = ref([
  {
    name:"home",
    label:"Home",
    // icon: "icon"
  },
  {
    name:"about",
    label:"About",
    // icon: "icon"
  }
])

function isRouteActive(routeName:string){
  return route.name === routeName
}

function navigate(routeName:string){
  router.push({name:routeName})
}
</script>

<template>
  <header>
    <!-- <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" /> -->

    <!-- <div class="wrapper"> -->
      <div class="w-full bg-black flex justify-center top-0 fixed">
        <h3 class="text-white text-center my-5 font-bold">TECH JOBS</h3>
    </div>

      <nav class="flex mx-auto  justify-center mt-20 mb-5">
        <div :class="isRouteActive(item.name) ? 'menu-active' : 'menu'" v-for="(item, idx) in sideMenu" :key="idx" @click="navigate(item.name)">
        <i class="mx-auto my-auto cursor-pointer" :class="item.icon"></i>
        <label class="cursor-pointer">{{item.label}}</label>
      </div>
      </nav>
    <!-- </div> -->
  </header>

  <RouterView />
</template>

<style scoped>
.menu{
  @apply w-auto my-auto mr-5 text-gray-500 px-2 py-3 hover:text-black font-semibold rounded-md cursor-pointer
}

.menu-active{
  @apply w-auto my-auto mr-5 bg-gray-100 text-black px-2 py-3 font-semibold  rounded-md cursor-pointer
}
</style>
