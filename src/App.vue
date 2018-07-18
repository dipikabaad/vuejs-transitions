<template>
  <div style="margin-top: 200px">
    <button class="btn btn-primary" @click="changeShape">Switch Shapes</button>
    <br><br>
    <transition name="fade" mode="out-in" appear>
    <component :is="shape"></component>
    </transition>
  </div>
</template>

<script>
import Square from './Square.vue';
import Circle  from './Circle.vue';
export default {
  data(){
    return {
      shape: 'appSquare'
    };
  },
 methods:{
  changeShape(){
    if(this.shape == 'appSquare'){
      this.shape = 'appCircle'
    } else {
      this.shape = 'appSquare'
    }
  }
 },
 components: {
  appSquare : Square,
  appCircle: Circle
 }
}
</script>

<style>
  .fade-enter-active, .fade-leave-active {
    transition: opacity 1s ease;
  }
  .fade-enter, .fade-leave-to {
    opacity: 0;
  }
</style>


