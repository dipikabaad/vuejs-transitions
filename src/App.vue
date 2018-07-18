<template>
  <div style="margin-top: 200px">
    <button class="btn btn-primary" @click="addRandom">Add Random Number</button>&nbsp;
    <button class="btn btn-primary" @click="removeRandom">Remove Random Number</button>
    <button class="btn btn-primary" @click="shuffle">Shuffle Numbers</button>
    <br><br>
    <transition-group name="fade">
    <span class="list-item" v-for="n in numbers" :key="n">{{n}}</span>
    </transition-group>
  </div>
</template>

<script>

export default {
  data(){
    return {
      numbers: [1,2,3,4,5,6,7,8,9,10]
    };
  },
 methods:{
  getRandomIndex(){
    return Math.floor(Math.random() * this.numbers.length);
   },
   addRandom(){
    let randomNumber = Math.floor(Math.random() * 100);
    this.numbers.splice(this.getRandomIndex(), 0, randomNumber);
   },
   removeRandom(){
    this.numbers.splice(this.getRandomIndex(),1)
   },
   shuffle(){
    this.numbers = _.shuffle(this.numbers);
   }
 }
}
</script>

<style>
  .list-item {
    display: inline-block;
    margin-right: 10px;
  }
  
  .fade-enter-active, .fade-leave-active {
    transition: all 1s;
  }
  
  .fade-enter, .fade-leave-to {
    opacity: 0;
    transition: rotate(45deg) translate(-32px);
  }
  
  .fade-move {
    transition: transform 1s;
  }

  .fade-leave-active {
    position: absolute;
  }
</style>


