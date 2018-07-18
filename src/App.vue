<template>
  <div style="margin-top: 200px">
    <button class="btn btn-primary" @click="show= !show">Toggle</button>
    <transition  enter-active-class="animated pulse slow"
    leave-active-class="animated zoomOut"
    >
    <p v-if="show" style="width: 200px;">Lorem ipsum dolar sit amet</p>
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
  .slow{
  animation-duration: 5s;
  }
</style>


