<template>

  <div class="backdrop" @dblclick.self="closeModal">
      <form @submit.prevent="verifyForm">
        <title>form</title>
        <label>Name</label>
        <input type="text" v-model="name" required>

        <label>Family Name</label>
        <input type="text" v-model="familyName" required>

        <div class="st">
          <div>
            <label>Street</label>
            <input type="text" v-model="street">
          </div>
          <div>
            <label>Street Number</label>
            <input type="number" min="1" max="100" placeholder="1-100" v-model="streetNo">
          </div>
        </div>

        <label>Email</label>
        <input type="email" v-model="email" required>
        
        <label>Password</label>
        <input type="password" title="password" v-model="password" required>

        <label>Nationality</label>
        <select v-model="nationality" title="select" required>
          <option value="" disabled selected hidden>Select</option>
          <option value="Afghan">Afghan</option>
          <option value="Albanian">Albanian</option>
          <option value="Algerian">Algerian</option>
          <option value="American">American</option>
          <option value="Andorran">Andorran</option>
          <option value="Angolan">Angolan</option>
          <option value="Antiguans">Antiguans</option>
        </select>

      <div class="terms">
        <input type="checkbox" required v-model="terms">
        <label>Accept terms and conditions</label>
      </div>

      <div class="submit">
        <button :disabled="((!terms) || (name==='') || (familyName==='') || (street==='') || (email==='') || (password==='') || (nationality===''))" type="submit">Create an Account</button>
      </div>

      </form>
  </div>

</template>


<script>
export default {
  data() {
    return {
      name: '',
      familyName: '',
      street: '',
      streetNo: '',
      email: '',
      password: '',
      nationality: '',
      terms: false,
      conditions: false
    }
  },
  methods: {
    closeModal() {
      this.$emit('close')
    },
    verifyForm() {
      this.$emit('verify')
    }
  }
}
</script>

<style>
form {
  max-width: 420px;
  margin: 100px auto;
  background: white;
  text-align: left;
  padding: 40px;
  border-radius: 10px;
}
label {
  color: #aaa;
  display: inline-block;
  margin: 25px 0 15px;
  font-size: 0.6em;
  text-transform: uppercase;
  letter-spacing: 1px;
  font-weight: bold;
}
.backdrop {
  top: 0 ;
  position: fixed;
  background: rgba(0,0,0,0.5);
  width: 100%;
  height: 100%;
}
input, select {
  background: #e0e0e0;
  display: block;
  padding: 10px 6px;
  width: 100%;
  box-sizing: border-box;
  border: none;
  border-bottom: 1px solid #555;
  color: #555;
  border-radius: 15px;
}
input[type="checkbox"] {
  display: inline-block;
  width: 16px;
  margin: 0 10px 0 0;
  position: relative;
  top: 2px;
}
.st {
  display: flex;
  justify-content: space-between;
}
.submit {
  text-align: center;
}

</style>