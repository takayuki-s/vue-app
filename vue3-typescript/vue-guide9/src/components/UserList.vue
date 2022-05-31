<template>
  <ul>
    <li v-for="user in users" :key="user" @click="removeUser(user)">
      {{ user }}
    </li>
  </ul>
  <div>
    <input type="text" v-model="inputtingUser">
    <button @click="addUser(inputtingUser)">Add User</button>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
const users = ref(["John", "Max", "Michael", "Julie"])
const inputtingUser = ref<string>("")
const addUser = (newUser: string) => {
  users.value.push(newUser)
  inputtingUser.value = ""
}

const removeUser = (user: string) => {
  users.value = users.value.filter(v => v != user)
}
</script>

<style scoped>
ul {
  list-style: none;
  margin: 1rem 0;
  padding: 0;
}

li {
  border: 1px solid rgb(104, 104, 104);
  padding: 1rem;
  text-align: center;
}
</style>