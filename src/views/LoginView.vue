<template>
  <form
    method="post"
    @submit="Submit"
  >
    <label for="uname"><b>Email</b></label>
    <input
      v-model="form.email"
      type="email"
      placeholder="Enter Email"
      required
    >
    <br><br>
    <label for="psw"><b>Password</b></label>
    <input
      v-model="form.password"
      type="password"
      placeholder="Enter Password"
      required
    >
    <br><br>
    <button type="submit">
      Login
    </button>
  </form>
  <br>
  {{ $store.state.email }}
</template>

<script>
export default {
  data() {
    return {
      form: {
        email: "",
        password: "",
      },
    }
  },
  methods: {
    Submit(event){
      event.preventDefault()
      this.$store.commit('login', this.form.email)
    },
  },
    
}
</script>
