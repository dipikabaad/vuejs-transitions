<template>
  <div style="margin-top: 200px">
    <button class="btn btn-primary" @click="show= !show">Toggle</button>
    <transition
    @before-enter="beforeEnter"
    @enter="enter">
    <p v-if="show">Lorem ipsum dolar sit amet</p>
    </transition>
  </div>
</template>

<script>
export default {
  data(){
    return {
      show: false
    };
  },
  methods:{
    beforeEnter(el){
      el.style.opacity = 0;
    },
    enter(el, done){
      let opacity = 0;
      const interval = setInterval(() => {
          opacity += 0.1;
          el.style.opacity = opacity;
          if (opacity > 0.9) {
            clearInterval(interval);
            done();
          }
      }, 100);
    }
  }
  
}
</script>


