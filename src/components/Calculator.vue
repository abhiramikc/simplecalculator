<template>
  <input
    type="number"
    maxlength="4"
    size="4"
    placeholder="number1"
    v-model.number="number1"
  />
  <select v-model="operand">
    <option value="+">+</option>
    <option value="-">-</option>
    <option value="*">*</option>
    <option value="/">/</option>
  </select>
  <input
    type="number"
    maxlength="4"
    size="4"
    placeholder="number2"
    v-model.number="number2"
  />
  <button type="button" @click="ComputeValue">Compute</button>
  <br />{{ result }}
</template>
<script>
export default {
  name: "Calculator",
  data() {
    return {
      number1: 0,
      number2: 0,
      operand: "",
      result: "",
    };
  },
  methods: {
    ComputeValue() {
      switch (this.operand) {
        case "+":
          this.result = this.number1 + this.number2;
          break;
        case "-":
          this.result = this.number1 - this.number2;
          break;
        case "*":
          this.result = this.number1 * this.number2;
          break;
        case "/":
          this.result = this.number1 / this.number2;
          break;
      }
    },
  },
};
</script>
<style>
input[type="number"],
select {
  width: 20%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  /*box-sizing: border-box; */
}
button {
  background-color: #4caf50;
  border: none;
  color: white;
  padding: 16px 32px;
  text-decoration: none;
  margin: 4px 2px;
  cursor: pointer;
}
</style>
