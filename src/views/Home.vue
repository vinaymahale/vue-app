<template>
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->

      <vue-tabs class="space" centered>
        <v-tab title="MENU">
        <MenuComponent class="padding-top" v-bind:dishes="dishes" v-on:addtotal="addTotal" v-on:subtotal="subTotal"/>
        </v-tab>

        <v-tab title="GALLERY"><br>
        <img alt="Vue logo" src="https://picsum.photos/id/1080/200/200">
        </v-tab>

    </vue-tabs>
    <div class="footer" v-if="total">
 <h2 >Total : Rs. {{ total }} </h2>
 </div>
  </div>


</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import MenuComponent from '../components/MenuComponent';
import {VueTabs, VTab} from 'vue-nav-tabs/dist/vue-tabs.js'
//you can also import this in your style tag
import 'vue-nav-tabs/themes/vue-tabs.css'

export default {
    name: "home",
    components : {
        VueTabs,
        VTab,
        MenuComponent
    },
    methods : {
      addTotal(price){
        this.total  = this.total + price;
      },
      subTotal(price){
        this.total  = this.total - price;
      }
    },
    data() {
    return {
      total : 0,
      dishes : [
        {
          id: 1,
          name : "Veg. Fried Rice",
          price : 150,
          count : 0
        },
        {
          id: 2,
          name : "Chicken Fried Rice",
          price : 200,
          count : 0
        },
        {
          id: 3,
          name : "Egg Fried Rice",
          price : 170,
          count : 0
        },
        {
          id: 4,
          name : "Paneer Butter Masala",
          price : 130,
          count : 0
        },
        {
          id: 5,
          name : "Veg. Biryani",
          price : 120,
          count : 0
        }
        ]
    }
  }
}
</script>

<style scoped>

.space {
  padding:50px 50px 50px 50px;
}

.padding-top {
  padding-top : 20px;
}

.footer {
   position: fixed;
   left: 0;
   bottom: 0;
   width: 100%;
   background-color: white;
   color: red;
   border-top: 4px solid red;
   text-align: center;
}
</style>