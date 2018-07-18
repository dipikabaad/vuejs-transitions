<template>
  <div style="margin-top: 200px">
    <button class="btn btn-primary" @click="show= !show">Toggle</button>
    <transition >
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
  .v-enter-active{
      animation: pulse 1s;
  }
  .v-leave-active{
    animation: fade-out 1s;
  }
  @keyframe fade-out {
      from {opacity: 1;
      transition: opacity;
      }
      to {
      opacity: 0;
      }
  }
  @keyframe pulse{
    from {
        transform: scaled(1,1,1);
    }

    50% {
      tranform: scaled(1.2,1.2,1.2);
    }

    to {
      transform: scaled(1,1,1);

    }
  }
</style>

