<template>
  <div class="app">
    <div class="form">
      <form>
        <input v-model="inputData" name="" id="input" placeholder="" />
      </form>
    </div>
    <div class="allnum">
      <div class="row">
        <button
          class="button"
          @click="setNum1"
          @mouseover="changeColor"
          @mouseleave="originalcolor"
        >
          1
        </button>
        <button
          class="button"
          @click="setNum2"
          @mouseover="changeColor"
          @mouseleave="originalcolor"
        >
          2
        </button>
        <button
          class="button"
          @click="setNum3"
          @mouseover="changeColor"
          @mouseleave="originalcolor"
        >
          3
        </button>
        <button
          class="fbutton"
          @click="setPlus"
          @mouseover="changeColor"
          @mouseleave="originalcolor"
        >
          +
        </button>
      </div>
      <div class="row">
        <button
          class="button"
          @click="setNum4"
          @mouseover="changeColor"
          @mouseleave="originalcolor"
        >
          4
        </button>
        <button
          class="button"
          @click="setNum5"
          @mouseover="changeColor"
          @mouseleave="originalcolor"
        >
          5
        </button>
        <button
          class="button"
          @click="setNum6"
          @mouseover="changeColor"
          @mouseleave="originalcolor"
        >
          6
        </button>
        <button
          class="fbutton"
          @click="setMinus"
          @mouseover="changeColor"
          @mouseleave="originalcolor"
        >
          -
        </button>
      </div>
      <div class="row">
        <button
          class="button"
          @click="setNum7"
          @mouseover="changeColor"
          @mouseleave="originalcolor"
        >
          7
        </button>
        <button
          class="button"
          @click="setNum8"
          @mouseover="changeColor"
          @mouseleave="originalcolor"
        >
          8
        </button>
        <button
          class="button"
          @click="setNum9"
          @mouseover="changeColor"
          @mouseleave="originalcolor"
        >
          9
        </button>
        <button
          class="fbutton"
          @click="setMultiply"
          @mouseover="changeColor"
          @mouseleave="originalcolor"
        >
          *
        </button>
      </div>
      <div class="row">
        <button
          class="zero"
          @click="setNum0"
          @mouseover="changeColor"
          @mouseleave="originalcolor"
        >
          0
        </button>
        <button
          class="button"
          @click="setDot"
          @mouseover="changeColor"
          @mouseleave="originalcolor"
        >
          ,
        </button>
        <button
          class="fbutton"
          @click="setDivide"
          @mouseover="changeColor"
          @mouseleave="originalcolor"
        >
          /
        </button>
      </div>
    </div>
    <div class="func">
      <button
        class="resclear"
        @click="setResult"
        @mouseover="changeColor"
        @mouseleave="originalcolor"
      >
        =
      </button>
      <button
        class="resclear"
        @click="clear"
        @mouseover="changeColor"
        @mouseleave="originalcolor"
      >
        C
      </button>
    </div>
  </div>
</template>


<script>
export default {
  data() {
    return {
      inputData: "",
      isPlus: false,
      isMinus: false,
      isMultiply: false,
      isDivide: false,
      result: 0,
      numOne: 0,
      numTwo: 0,
      newRound: false,
    };
  },
  methods: {
    setNum1() {
      if (this.newRound) {
        this.newRound = false;
        this.inputData = "";
      }
      this.inputData += "1";
    },
    setNum2() {
      if (this.newRound) {
        this.newRound = false;
        this.inputData = "";
      }
      this.inputData += "2";
    },
    setNum3() {
      if (this.newRound) {
        this.newRound = false;
        this.inputData = "";
      }
      this.inputData += "3";
    },
    setNum4() {
      if (this.newRound) {
        this.newRound = false;
        this.inputData = "";
      }
      this.inputData += "4";
    },
    setNum5() {
      if (this.newRound) {
        this.newRound = false;
        this.inputData = "";
      }
      this.inputData += "5";
    },
    setNum6() {
      if (this.newRound) {
        this.newRound = false;
        this.inputData = "";
      }
      this.inputData += "6";
    },
    setNum7() {
      if (this.newRound) {
        this.newRound = false;
        this.inputData = "";
      }
      this.inputData += "7";
    },
    setNum8() {
      if (this.newRound) {
        this.newRound = false;
        this.inputData = "";
      }
      this.inputData += "8";
    },
    setNum9() {
      if (this.newRound) {
        this.newRound = false;
        this.inputData = "";
      }
      this.inputData += "9";
    },
    setNum0() {
      if (this.newRound) {
        this.newRound = false;
        this.inputData = "";
      }
      this.inputData += "0";
    },
    setDot() {
      if (this.newRound) {
        this.newRound = false;
        this.inputData = "";
      }
      this.inputData += ".";
    },

    setPlus() {
      this.isPlus = true;
      this.numOne = parseFloat(this.inputData);
      this.inputData = "";
      document.getElementById("input").setAttribute("placeholder", "+");
      console.log(this.numOne);
    },
    setMinus() {
      this.isMinus = true;
      this.numOne = parseFloat(this.inputData);
      this.inputData = "";
      document.getElementById("input").setAttribute("placeholder", "-");
      console.log(this.numOne);
    },
    setMultiply() {
      this.isMultiply = true;
      this.numOne = parseFloat(this.inputData);
      this.inputData = "";
      document.getElementById("input").setAttribute("placeholder", "*");
      console.log(this.numOne);
    },
    setDivide() {
      this.isDivide = true;
      this.numOne = parseFloat(this.inputData);
      this.inputData = "";
      document.getElementById("input").setAttribute("placeholder", "/");
      console.log(this.numOne);
    },

    setResult() {
      this.numTwo = parseFloat(this.inputData);

      if (this.isPlus) {
        this.inputData = this.numOne + this.numTwo;
        this.isPlus = false;
      } else if (this.isMinus) {
        this.inputData = this.numOne - this.numTwo;
        this.isMinus = false;
      } else if (this.isMultiply) {
        this.inputData = this.numOne * this.numTwo;
        this.isMultiply = false;
      } else if (this.isDivide) {
        this.inputData = this.numOne / this.numTwo;
        this.isDivide = false;
      }

      this.newRound = true;
      console.log(this.numOne);
    },

    clear() {
      this.inputData = "";
      document.getElementById("input").setAttribute("placeholder", "");
    },

    changeColor: function (event) {
      event.target.style.backgroundColor = "#F9A9A9";
    },
    originalcolor: function (event) {
      event.target.style.backgroundColor = "white";
    },
  },
};
</script>


<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  padding: 20px;
  margin-top: 50px;
}

.form {
  display: flex;
  justify-self: center;
  flex-direction: column;
}

input {
  width: 330px;
  border: solid teal;
  padding: 10px 15px;
  margin-top: 15px;
  font-size: 40px;
}

.button {
  align-self: flex-end;
  margin-top: 15px;
  padding: 10px 15px;
  background: none;
  color: blue;
  border: 1px solid teal;
  width: 70px;
  height: 70px;
  font-size: 40px;
  margin: 1px;
}

.zero {
  align-self: flex-end;
  margin-top: 15px;
  padding: 10px 15px;
  background: none;
  color: blue;
  border: 1px solid teal;
  width: 140px;
  height: 70px;
  font-size: 40px;
  margin: 1px;
}

.fbutton {
  align-self: flex-end;
  margin-top: 15px;
  padding: 10px 15px;
  background: none;
  color: green;
  border: 1px solid teal;
  width: 70px;
  height: 70px;
  font-size: 40px;
  margin-left: 40px;
}

.resclear {
  align-self: flex-end;
  margin: 20px;
  padding: 10px 15px;
  background: none;
  color: red;
  border: 1px solid teal;
  width: 140px;
  height: 70px;
  font-size: 40px;
}
</style>