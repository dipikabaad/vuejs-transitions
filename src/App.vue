<template>
  <div style="margin-top: 200px">
    <button class="btn btn-primary" @click="show= !show">Toggle</button>
    <transition name="fade">
    <p v-if="show" style="width: 200px;">Lorem ipsum dolar sit amet</p>
    </transition>
    <transition name="pulse-fade">
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
  .fade-enter, fade-leave-to, pulse-fade-enter, pulse-fade-leave-to{
    opacity: 0;
  }
  .fade-enter-active, fade-leave-active {
    transition: opacity 1s;
  }

  .pulse-fade-enter-active{
    transition: opacity .5s;
    animation: pulse 1s;
  }
  .pulse-fade-leave{
    opacity: 1;
  }
  .pulse-fade-leave-active{
    transition: opacity 1s;
    animation: pulse 1s;
  }

  @keyframe pulse{
    from {
      transform: scaled(1,1,1);
    }
    50% {
      transform: scaled(1.2,1.2,1.2);
    }
    to {
      transform: scaled(1,1,1);
    }
  }
</style>

