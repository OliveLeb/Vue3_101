<template>
  <!-- <h1>Hello World !</h1>
  <Avatar name='CESAR' badgeColor='#5ad539' image='https://images.unsplash.com/photo-1522075469751-3a6694fb2f61?ixid=MXwxMjA3fDB8MHxzZWFyY2h8MXx8cHJvZmlsZSUyMHBpY3R1cmV8ZW58MHwyfDB8&ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=60' />
  <ProfilCard :pro='true' name='Ricky Park' 
  img='https://randomuser.me/api/portraits/women/79.jpg' 
  city='New York' job='Front end developper'
  :skills="['UI / UX','HTML','CSS','JavaScript','React','Node']"
  />
  <InputSpinner v-for="(counter,i) in initCounters" :initCounter="counter" :key="i" :step="10"/> -->
  <Movie />
</template>

<script>
// import Avatar from './components/Avatar.vue';
// import ProfilCard from './components/ProfilCard.vue';
// import InputSpinner from './components/InputSpinner.vue';
import Movie from './components/Movie.vue';

export default {
    name: 'App',
    components: {
      // Avatar,
      // ProfilCard,
      // InputSpinner,
      Movie,
    },
    data() {
      return {
        initCounters : [0,0,20,0,40,65]
      }
    }
}
</script>

<style>
@import url(https://maxcdn.bootstrapcdn.com/font-awesome/4.6.3/css/font-awesome.min.css);

    body{
      font-family: Arial, sans-serif;
    }
    h1 {
      text-align: center;
      color: #2c3e50;
      margin-top: 60px;
    }
</style>