<template>
  <div class="container">
    <button type="button" class="btn btn-primary">{{ msg }}</button>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "Ping",
  data() {
    return {
      msg: "Hello",
    };
  },
  methods: {
    async getMessage() {
      const response = await axios.get("http://localhost:5000/ping");
      this.msg = response.data;
      console.log(response);
    },
  },
  beforeMount() {
    this.getMessage();
  },
};
</script>
