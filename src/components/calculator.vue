<template>
  <div id="main">
    <div class="calc">
      <div class="heading">
        <h1>Calculator</h1>
      </div>

      <div class="input-field" style="">
        {{ calculatorValue || 0 }}
      </div>

      <div class="row no-gutters input-btn">
        <div
          class="col-2 m-1 text-white"
          v-for="n in calculatorNums"
          :key="n"
          @click="action(n)"
        >
          <button class="bt">{{ n }}</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      calculatorValue: "",
      calculatorNums: [
        "c",
        "+",
        "-",
        "*",
        "%",
        "/",
        "=",
        ".",
        0,
        1,
        2,
        3,
        4,
        5,
        6,
        7,
        8,
        9,
      ],
    };
  },
  methods: {
    action(n) {
      if (!isNaN(n) || n === ".") {
        this.calculatorValue += n + "";
      }
      /* clearing value */
      if (n === "c") {
        this.calculatorValue = "";
      }
      /* percentage */
      if (n === "%") {
        this.calculatorValue = this.calculatorValue / 100 + "";
      }
      if (n === "=") {
        this.calculatorValue = eval(
          this.previousCalculatorValue + this.oprator + this.calculatorValue
        );
        this.previousCalculatorValue = "";
        this.oprator = null;
      }
      if (n == "+") {
        this.oprator = n;
        this.previousCalculatorValue = this.calculatorValue;
        this.calculatorValue = "";
      }
      if (n == "-") {
        this.oprator = n;
        this.previousCalculatorValue = this.calculatorValue;
        this.calculatorValue = "";
      }
      if (n == "*") {
        this.oprator = n;
        this.previousCalculatorValue = this.calculatorValue;
        this.calculatorValue = "";
      }
      if (n == "/") {
        this.oprator = n;
        this.previousCalculatorValue = this.calculatorValue;
        this.calculatorValue = "";
      }
    },
  },
};
</script>

<style>
.input-field {
  padding: 10px;
  color: #fff;
  background-color: #252525;
  font-size: 21px;
  text-align: right;
  margin: 50px auto;
  border: 1px solid #333;
  border-radius: 10px;
}
.input-field:hover {
  background-color: #333;
}
.bt {
  padding: 20px 30px;
  color: white;
  border-radius: 15px;
  background: #494949;
  flex: 1;
  margin: 10px 5px 0;
  width: calc(20% - 10px);
  border: none;
}
button:hover {
  background-color: #333;
}
.heading {
  color: #fff;
  font: 1em poppins;
  text-align: center;
}
#main {
  margin: 100px auto;
  max-width: 500px;
  background-color: #141414;
  border-radius: 15px;
  padding: 20px;
}
.calc {
  background: #1f1f1f;
  border-radius: 15px;
  padding: 30px;
  border: 1px solid #333;
}
.input-btn {
  border-radius: 15px;
  border: 1px solid #333;
  padding: 20px 0;
}
</style>
