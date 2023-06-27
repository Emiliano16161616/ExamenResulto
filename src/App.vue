<script setup>
import { ref } from 'vue';
import cardComponent1 from './components/cardComponent1.vue';
import cardComponent2 from './components/cardComponent2.vue';
import cardComponent3 from './components/cardComponent3.vue';

let codigo=ref();
let modulo=ref();
let contador=ref(0);
let modulos1= ref([]);
let modulos2= ref([]);
let modulos3= ref([]);

const enviar=function(){
  if(modulo.value==1){
    modulos1.value.push(codigo.value);
    contador.value++;
  }
  if(modulo.value==2){
    modulos2.value.push(codigo.value);
    contador.value++;
  }
  if(modulo.value==3){
    modulos3.value.push(codigo.value);
    contador.value++;
  }
}


</script>

<template>
  <div class="flex gap-3 mx-2 bg-white">
    <div class="flex-1">
      <div class="p-1 bg-blue-700 ">
        MODULO 1
      </div>
      <cardComponent1 v-for="(modulo1,indice) in modulos1" :key="indice" :codigo="modulo1" :indice="indice"/>
    </div>

    <div class="flex-1">
      <div class="p-1 bg-orange-700">
        MODULO 2
      </div>
      <cardComponent2 v-for="(modulo2,indice) in modulos2" :key="indice" :codigo="modulo2" :indice="indice"/>
    </div>

    <div class="flex-1">
      <div class="p-1 bg-green-700">
        MODULO 3
      </div>
      <cardComponent3 v-for="(modulo3,indice) in modulos3" :key="indice" :codigo="modulo3" :indice="indice"/>
    </div>
  </div>
  <div class="flex mt-5 bg-white">
    <div class="flex ml-3">
      <div>
        {{ contador }}
      </div>
      <h2 class="ml-2 ">
        TURNOS
      </h2>
    </div>
    
    <div>
      <input type="text" placeholder="Codigo" class="border-[1px] border-black ml-10 rounded-lg" v-model="codigo">
    </div>
    
    <div>
      <input type="number" placeholder="Modulo" class="border-[1px] border-black ml-10 rounded-lg" v-model="modulo">
    </div>
    
    <button class="p-1 ml-10 text-white rounded-lg cursor-pointer bg-violet-400" @click="enviar"> Agregar Turno</button>


    
  </div>
</template>