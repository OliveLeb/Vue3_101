<template>
  <h1>Hello World !</h1>
  <Avatar name='CESAR' badgeColor='#5ad539' image='https://images.unsplash.com/photo-1522075469751-3a6694fb2f61?ixid=MXwxMjA3fDB8MHxzZWFyY2h8MXx8cHJvZmlsZSUyMHBpY3R1cmV8ZW58MHwyfDB8&ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=60' />
</template>

<script>
import Avatar from './components/Avatar.vue';

export default {
    name: 'App',
    components: {
      Avatar,
    }
}
</script>

<style>
    h1 {
      font-family: Arial, sans-serif;
      text-align: center;
      color: #2c3e50;
      margin-top: 60px;
    }
</style>