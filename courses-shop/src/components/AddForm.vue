<template>
  <div class="form-add-course">
    <form @submit.prevent="addPromocode">
      <p>введите промокод</p>
      <input type="text" placeholder="введите промокод" v-model="inputText" >
      <button>ок</button>
    </form>
    <p>{{ text }}</p>
    <button class="esc" @click="emit('close-form')">✖</button>
  </div>
</template>

<script setup>
import {ref} from 'vue'
const emit = defineEmits(['add-promocode', 'close-form'])
const inputText = ref('')



function addPromocode(){
  emit('add-promocode', inputText.value)
}

</script>

<style scoped>
.form-add-course{
  width: 400px;
  height: 200px;
  background-color: rgb(197, 202, 198) ;
  text-align: center;
  margin: -30% 0 0 35%;
  position: absolute;
}
form{
  padding-top: 15%;
}

.esc{
  margin: -30% 0 0 39%;
  position: absolute;
}
</style>