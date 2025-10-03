<template>
   <div> 
    <!--<h1 v-if="isLoggedIn">Welcome back</h1>
    <h1 v-else>You need to login</h1> -->

    <h1>{{ isLoggedIn ? 'Welcome back' : 'You need to login' }}</h1>
  </div>
</template>

<script>
export default {
data() {
    return {
      isLoggedIn: true, 
    };
  },
}</script>