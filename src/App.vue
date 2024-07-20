<template>
  <button @click="(isRegister = true) && (isVerify = false)">Register</button>
  <p class="verified" v-if="isVerify">Successfully Registered</p>
  <div v-if="isRegister">
    <RegisterForm  @close="isRegister = false" @verify="(isVerify = true) && (isRegister = false)">
      <h1>Sigma Giveaway</h1>
      <p>"Grab here"</p>
    </RegisterForm>
  </div>

</template>

<script>
import RegisterForm from './components/RegisterForm.vue'

export default {
  name: 'App',
  components: { RegisterForm
  },
  data() {
    return {
      isRegister: false,
      isVerify: false
    }
  }
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
.verified {
  color: green;
  font-weight: bold;
  font-size: 20px;
  margin-top: 20px;
  
}
</style>
