<template>
  <div>
    <courses-list :courses="courses" @click-on-button="openForm"/>
    <add-form v-if="formIsOpen" @close-form="closeForm" @add-promocode="addPromocode" /> 
    
  </div>
</template>

<script setup>
import CoursesList from "./components/CoursesList.vue"
import AddForm from "./components/AddForm.vue"
import {ref} from 'vue'


const formIsOpen = ref(false)

function openForm(){
  formIsOpen.value = true
}

function closeForm(){
  formIsOpen.value = false
}

function addPromocode(promocode){
  if(promocode.trim() == ''){
    alert('введите промокод')
  }
  else{
    for(let i = 0; i<courses.value.length; i++){
      if (promocode == courses.value[i].promocode){
        courses.value[i].isBought = true
        setTimeout(function() {alert('вы приобрели курс')}, 1000)
      } else {
        
      }
    }
    closeForm()
  }
}

const courses = ref([
  {
    num: 0,
    name: "Пользователь",
    price: "0 ₽",
    isBought: false,
    promocode: 110,
  },
  {
    num: 1,
    name: "Любитель",
    price: "5 000₽",
    isBought: false,
    promocode: 111,
  },
  {
    num: 2,
    name: "Профессионал",
    price: "25 000₽",
    isBought: false,
    promocode: 222,
  },
  {
    num: 3,
    name: "Консультант",
    price: "75 000 ₽",
    isBought: false,
    promocode: 333,
  },
  {
    num: 4,
    name: "Эксперт",
    price: "200 000₽",
    isBought: false,
    promocode: 444,
  },
  {
    num: 5,
    name: "Амбассадор",
    price: "1 000 000₽",
    isBought: false,
    promocode: 555,
  },
])
</script>
