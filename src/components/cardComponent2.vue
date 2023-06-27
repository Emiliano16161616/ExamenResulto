<script setup>
const props=defineProps({
    codigo:{
        type: String,
        default:"no hay codigo :V"
    },
    indice:{
        type: Number,
        default:0
    }
})
</script>

<template>
  <div class="flex items-center justify-center mx-2 bg-white">
    <div>
        {{ props.indice+1 }} - {{ props.codigo }}
    </div>
  </div>
</template>