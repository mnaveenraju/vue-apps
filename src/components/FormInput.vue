<template>
  <div class="signup-form">
    <div class="inner-signup-form">
      <h2>Sample input Fields</h2>
      <form @submit="submit" ref="FormInput">
        <label for="">Email</label>
        <input type="text" placeholder="Email" v-model="email" />

        <label for="">Password</label>
        <input type="password" placeholder="Password" v-model="password" />

        <label for="">Role</label>
        <select v-model="role">
            <option value="Manager">Manager</option>
            <option value="Developer">Developer</option>
        </select>

        <label for="">Skills</label>
        <input type="text" placeholder="Skill" v-model="tempSkill" @keyup.ctrl="addSkill">
        <p class="skill-note">Note: Press "ctrl + enter" to add mulltiple skills</p>
        <div class="skills">
          <span v-for="skill in skills" :key="skill" class="skill">{{skill}}</span>
        </div>

        <div class="terms">
          <input type="checkbox">
          <label for="">I agree terms and conditions</label>
        </div>

        <button type="submit">Submit</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "FormInput",
  data() {
    return {
      email: "",
      password: "",
      role: "",
      tempSkill: "",
      skills: []
    };
  },
  methods: {
    submit(event) {
      console.log("submit", this.email, this.password);
      event.preventDefault();
    },
    addSkill(e) {
      if (e.key === "Enter" && !this.skills.includes(this.tempSkill)) {
        this.skills.push(this.tempSkill)
      }
      this.tempSkill = ""
    }
  },
};
</script>

<style>
.inner-signup-form h2 {
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
  margin: 9vh auto;
  width: 23em;
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

input, select {
  height: 20px;
  border: 1px solid #c2b4b4ee;
  padding: 5px 0px;
  border-top: none;
  border-left: none;
  border-right: none;
}

select {
    padding: unset;
}

input:focus, select:focus {
  outline: none;
  box-shadow: 0 10px 10px -10px #c2b4b4ee;
  border-top: none;
  border-left: none;
  border-right: none;
}

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

.terms {
  display: flex;
  align-items: center;
}

.terms label {
  margin-left: 10px;
}

.skills {
  display: flex;
  flex-wrap: wrap;
}

.skills .skill {
  margin: 6px 6px 0px 0px;
    background: #f1ecec;
    padding: 5px 10px;
    border-radius: 8px;
    font-size: 14px;
}

.skill-note  {
    margin: 10px 0px;
    font-size: 12px;
    text-align: left;
    color: #968f8f;
}
</style>
