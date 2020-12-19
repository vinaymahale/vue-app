<template>
    <tr>
        <td>  <br><img alt="Vue logo" class="img-round"  src="https://picsum.photos/id/1080/100/100"> </td>
        <td> <br><h3>{{ dish.name }}</h3> <p> Rs. {{ dish.price }}</p> </td>
        <td> <br>
            <p v-if="dish.count"> <button class="button-2" @click='sub'> - </button> <span class="f-20">{{ dish.count }}</span> <button class="button-2" @click='add'> + </button></p>
            <p v-else> <button class="button" @click='add'>Add</button></p>
         </td>
        </tr>
</template>


<script>
export default {
    name: "MenuItem",
    props: ["dish"],
    methods: {
    add () {
        this.dish.count = this.dish.count + 1;
        this.$emit('addtotal', this.dish.price)
    },
    sub () {
        this.dish.count = this.dish.count - 1;
        this.$emit('subtotal', this.dish.price)
    }
  }  
}
</script>

<style scoped>

 td {
    width: 400px;
 }

 .img-round {
    border-radius: 17px 17px 17px 17px;
  }


   .button{
    border-radius: 17px 17px 17px 17px;
    border: 2px solid #73AD21;
    padding: 10px;
    width: 60px;
    outline:none;
    font-size: 20px;  
  }

  .f-20 {
    font-size: 20px;
    padding : 5px;
   }

  .button-2{
    border-radius: 17px 17px 17px 17px;
    border: 2px solid #73AD21;
    padding: 0px;
    width: 60px;
    outline:none;
    font-size: 25px;  
  }

</style>