<!-- eslint-disable prettier/prettier -->
<!-- eslint-disable prettier/prettier -->
<script setup>
import { RouterLink, RouterView } from 'vue-router'
import MyComponentA from "./components/Menu.vue";
import MyComponentB from "./components/test.vue";
import './style.css'
</script>

<template>
  

  <div class="flex flex-col h-screen">
    <nav class="flex items-center justify-between flex-wrap bg-gray-800 p-6">
      <div class="flex items-center text-white mr-6">
        <button class="inline-block text-sm px-4 py-2 leading-none border rounded text-white border-white hover:border-transparent hover:text-gray-800 hover:bg-white mt-4 lg:mt-0 mr-2">
          <router-link to="/">Home</router-link>
        </button>
        <button class="inline-block text-sm px-4 py-2 leading-none border rounded text-white border-white hover:border-transparent hover:text-gray-800 hover:bg-white mt-4 lg:mt-0 mr-2">
        Orders
        </button>
        <button class="inline-block text-sm px-4 py-2 leading-none border rounded text-white border-white hover:border-transparent hover:text-gray-800 hover:bg-white mt-4 lg:mt-0 mr-auto">
          <router-link to="/about">Menu</router-link>
          
        </button>
        <div>
    <button @click="showComponent('A')">Show Component A</button>
    <button @click="showComponent('B')">Show Component B</button>

  </div>


      </div>
      <div class="flex items-center text-white mr-auto">
        <span class="font-semibold text-xl tracking-tight mx-auto">Restaurant Name</span>
      </div>
      
      <div class="flex items-center text-white">
        <button class="inline-block text-sm px-4 py-2 leading-none border rounded text-white border-white hover:border-transparent hover:text-gray-800 hover:bg-white mt-4 lg:mt-0 mr-2">
          Logout
        </button>
      </div>
      
    </nav>
    <keep-alive>
      <component :is="activeComponent"></component>
    </keep-alive>
    
  </div>





</template>

<style scoped>

</style>

<script>


export default {
  components: {
    MyComponentA,
    MyComponentB

  },
  data() {
    return {
      activeComponent: null
    };
  },
  methods: {
    showComponent(component) {
      if (component === "A") {
        this.activeComponent = "MyComponentA";
      } else if (component === "B") {
        this.activeComponent = "MyComponentB";
      }
    }
  }
};;
</script>