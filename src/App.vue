<template>
<RouterLink to="/UserForm">UserForm</RouterLink><br />
<RouterLink to="/HelloWorld">HelloWorld</RouterLink><br />
<RouterLink to="/HomeComponents">HomeComponents</RouterLink><br />
<RouterLink to="/TestingApi">Testing API</RouterLink><br />
<RouterLink to="/ToDoList">ToDoList</RouterLink><br />
<router-view></router-view>
<!-- <HomeComponents />  -->
<!-- <UserForm/> -->
</template>

<script>
// import { RouterLink } from 'vue-router';
// import HelloWorld from './components/HelloWorld.vue'
// import UserForm from './components/UserForm.vue';
//  import HomeComponents from './components/HomeComponents.vue';
// import TesingAPI from './components/TesingAPI.vue';
// import UserForm from './components/UserForm.vue';
export default {
    name: 'App',
//     components: {
//         // TesingAPI
//     // HelloWorld,
//     // RouterLink,HomeComponents,
//     // UserForm
// }
}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
