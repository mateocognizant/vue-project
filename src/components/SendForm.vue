<template>
  <div class="form-div">
    <form>
      <label for="fname">First Name</label>
      <input type="text" id="fname" v-model="name" name="firstname" placeholder="Your name.." />
      <label for="lname">Last Name</label>
      <input
        type="text"
        id="lname"
        v-model="surname"
        name="lastname"
        placeholder="Your last name.."
      />
      <div>
        <button @click="loadData()">Send</button>
      </div>
    </form>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "send-form",
  data() {
    return {
      name: "",
      surname: ""
    };
  },
  methods: {
    loadData() {
      let json = { name: this.name, surname: this.surname }
      this.name == "" || this.surname == ""
        ? alert("Information is missing")
        : axios
            .post("http://localhost:5000/data", json)
            .then(response => alert("Request succeed"))
            .catch(error => {
              alert("Request failed");
            });
      return;
    }
  }
};
</script>

<style lang="scss">
input[type="text"],
select {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}

input[type="submit"] {
  width: 100%;
  background-color: #4caf50;
  color: white;
  padding: 14px 20px;
  margin: 8px 0;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

input[type="submit"]:hover {
  background-color: #45a049;
}

.form-div {
  border-radius: 5px;
  background-color: #f2f2f2;

  label {
    font-size: 16px;
  }

  form {
    padding: 30px;
  }

  button {
    background-color: #4caf50; /* Green */
    border: none;
    color: white;
    padding: 15px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    width: 100%;
    cursor: pointer;
  }
}
</style>
