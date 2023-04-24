<template>
  <div>
    <button @click="pluss">
      Øk
    </button>

    {{ tall }}
  </div>
</template>
  
<script setup>
import { ref } from 'vue';

const tall = ref(0);

function pluss() {
  tall.value++;
}
</script>