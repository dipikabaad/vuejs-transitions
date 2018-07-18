<template>
  <div style="margin-top: 200px">
    <button class="btn btn-primary" @click="show= !show">Toggle</button>
    <transition name="fade">
    <p v-if="show" key="lorem-ipsum">Lorem ipsum dolar sit amet</p>
    <p v-else key="nohting-around-here">Nothing to see here</p>
    </transition>
  </div>
</template>

<script>
export default {
  data(){
    return {
      show: false
    };
  }
  
}
</script>
<style>
 .fade-enter, fade-leave-to {
    opacity: 0
 }
 .fade-enter-active, .fade-leave-active {
  transition: opacity 1s;
 }
</style>

