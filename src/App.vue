<template>
  <div style="margin-top: 200px">
    <button class="btn btn-primary" @click="show= !show">Toggle</button>
    <transition name="fade" appear
    appear-class=""
      appear-active-class=""
      appear-to-class="">
    <p v-if="show" key="lorem-ipsum">Lorem ipsum dolar sit amet</p>
    </transition>
  </div>
</template>

<script>
export default {
  data(){
    return {
      show: true
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

