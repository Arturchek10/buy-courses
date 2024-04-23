<template>
  <div>
    <h1 style="margin: 0 0 30px 40%;">Курсы</h1>
    <div style="display: flex; justify-content: space-around;">
      <p><b>№ курса</b></p>
      <p><b>название</b></p>
      <p><b>цена</b></p>
      <p><b>покупка</b></p>
    </div>
    <div class="listCourses" v-for="(el,index) in courses" 
    :card="el"
    :key="index"
    >
      <hr >
        <div style="display: flex; justify-content: space-around; align-items: right;">
          <p>{{ el.num }}</p>
          <p style="width: 100px;">{{ el.name }}</p>
          <p>{{ el.price }}</p>
          <p v-if="!el.isBought">❌</p>
          <p v-else>✅</p>
        </div>
    </div>
    <hr>
    <div>
      <button class="add-button" @click="$emit('click-on-button')">добавить</button>
    </div>
  </div>
  </template>

<script setup>
import {ref} from "vue"

const props = defineProps({
  num:{
    type: Number
  },
  courses:{
    type: Array
  },
  card:{
    type: Object
  }
})


</script>

<style scoped>
.add-button{
  color: white;
  font-size: 22px;
  font-weight: 500;
  margin-left: 80%;
  width: 200px;
  height: 60px;
  background-color: rgb(26, 234, 67);
  border: 0cap;
  cursor: pointer;
  opacity: 0.6;
}
.add-button:hover{
  transform: scale(1.02);
  opacity: 1;
}
.add-button:active{
  transform: scale(1.05);
  opacity: 1;

}
</style>