<template>
  <div class="signup-form">
    <div class="inner-signup-form">
      <h2>Create a new Account</h2>
      <form @submit="signup" ref="signupForm">
        <label for="">Email</label>
        <input type="text" placeholder="Email" v-model="email"/>

        <label for="">Password</label>
        <input type="password" placeholder="Password" v-model="password"/>

        <button type="submit">Signup</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "SignupForm",
  data() {
    return {
      email: "",
      password: "",
    }
  },
  methods: {
      signup(event) {
          console.log('signup', this.email, this.password);
        event.preventDefault();
      }
  }
};
</script>

<style>
.signup-form {
  background-color: #f9cfcf;
  padding: 20px 8px 8px 8px;
  width: 22em;
  border-radius: 6px;
  margin: 23vh auto;
box-shadow: 0px 1px 5px 0px #b98282;
}

.signup-form h2 {
  margin-top: 5px;
  margin-bottom: 5px;
  font-weight: bold;
}

.inner-signup-form {
  background-color: #ffff;
  display: flex;
  flex-direction: column;
  padding: 28px;
  border-radius: 10px;
}

form {
  display: contents;
}

label {
  text-align: start;
  margin: 10px 0px;
  font-weight: bold;
  font-size: 12px;
}

input {
  height: 20px;
  border-radius: 6px;
  border: 1.5px solid #c2b4b4ee;
  padding: 5px;
}

input:focus {
outline: none;
    box-shadow: 0px 0px 3px 0px;}

.signup-form button {
  padding: 7px;
  width: 8em;
  margin: 10px auto 0px auto;
  border-radius: 6px;
  color: #2c3e50;
  background-color: #8bf591;
    border: none;
    box-shadow: 0px 0px 4px 0px #8bf591;
}
</style>
