<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      For a guide and recipes on how to configure / customize this project,<br />
      check out the
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener"
        >vue-cli documentation</a
      >.
    </p>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  methods: {
    async test() {
      console.log(2);
      const newEmployee = {
        first_name: "Sebastian1",
        email: "sebastian@codingthesmartway.com",
      };
      for (let i = 0; i < 50; i++) {
        const resp = await axios.patch(
          `http://localhost:3000/employees/${(i % 5) + 1}`,
          newEmployee
        );
        console.log(resp.data);
      }
    },
  },
  mounted() {
    this.test();
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
