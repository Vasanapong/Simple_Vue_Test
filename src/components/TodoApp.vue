<template>
  <div class="todo-app">
    <form class="todo-app__form" @submit.prevent="handleSubmit()">
      <div class="todo-app__title">Todo App</div>
      <div class="todo-app__username">
        <label>username:</label><br />
        <input type="text" v-model.trim="this.username"/>
      </div>
      <div class="todo-app__email">
        <label>email:</label><br />
        <input type="email" v-model.trim="this.email"/>
      </div>
      <div class="todo-app__password">
        <label>password:</label><br />
        <input type="password" v-model.trim="this.password" autocomplete=""/>
      </div>
      <div class="todo-app__submit">
        <input type="Submit">
      </div>
    </form>
    <button @click="previewAllUser()">View All User</button>
  </div>
</template>

<script>
export default {
  name: "TodoApp",
  data(){
    return{
      username:"",
      email:"",
      password:"",
      userArray:[]
    }
  },
  methods:{
    handleSubmit(){
      let userData = {
        username:this.username,
        email:this.email,
        password:this.password,
        id:Date.now().toString()
      }
      this.userArray.push(userData)
    },
    previewAllUser(){
      console.log(this.userArray)
    }
  }
};
</script>

<style scoped>
.todo-app {
  display: grid;
  justify-items: center;
  align-items: center;
}
.todo-app__form {
  width: 100%;
  max-width: 600px;
}
.todo-app__form > div {
  margin: 20px 0px;
}
.todo-app__title {
  text-align: center;
  font-weight: 600;
}
.todo-app__username {
  padding: 0px 50px;
}
.todo-app__username > input {
  width: 100%;
}
.todo-app__email {
  padding: 0px 50px;
}
.todo-app__email > input {
  width: 100%;
}
.todo-app__password {
  padding: 0px 50px;
}
.todo-app__password > input {
  width: 100%;
}
.todo-app__submit {
  padding: 0px 50px;
}
input{
  margin: 10px 0px;
  padding: 5px;
}
</style>