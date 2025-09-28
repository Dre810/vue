<template>
  <div class="header">

    <h1>{{ title }}</h1>
    <p>{{ description }}</p>

      <button @click="alertMessage">Read More</button>
  </div>

  <!-- main comp will be here -->
  <MainComp/>
</template>

<script>

import MainComp from './components/MainComp.vue';

export default {
  //properties
  data(){
    return{
      title:"Hello world",
      description:"Lorem, ipsum dolor sit amet consectetur adipisicing elit. Cupiditate iure tempora optio dolorum non, earum ab aliquam fugiat illo laudantium cumque excepturi expedita ut. Voluptatum quasi perspiciatis molestiae impedit incidunt.",
    };
  },
  //methods
  methods:{
    alertMessage() {
      alert("Hello, you clicked on readmore");
    },
  },

  components: {
    MainComp,
  }
};
</script>

<style scoped>
h1{
  color: blue;
}
.header{
  background-color: chartreuse;
  padding: 10px;
  text-align: center;
}
</style>