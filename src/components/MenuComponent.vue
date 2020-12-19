<template>
<div class="menu-component">

    <table class="tbl-layout">    
    <tbody>
    <div v-bind:key="dish.id" v-for="dish in dishes">
        <MenuItem v-bind:dish="dish" v-on:addtotal="$emit('addtotal', dish.price)" v-on:subtotal="$emit('subtotal', dish.price)"/>
    </div>
    </tbody>
    </table>
</div>
</template>


<script>
import MenuItem from './MenuItem.vue'
export default {
    name: "menuComponent",
    components : {
        MenuItem
    },
    props: ["dishes"]
}
</script>
