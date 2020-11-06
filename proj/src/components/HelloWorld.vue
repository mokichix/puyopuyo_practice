<template>
<div class="main-field">
  <div class="left-field">
    <div class="ojama-field">
    </div>
    <div class="play-field">
      <div v-for="row in state" v-bind:key="row.id">
        <div v-for="cell in row" v-bind:key="cell.id" v-bind:class="{ red : cell }"></div>
      </div>
    </div>
  </div>
  <div class="next-field">
    <button @click="start">start</button>
  </div>
</div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  methods: {
    start: function () {
      setInterval(this.mainroop, 3000);
    },
    mainroop: function () {
      let pos = [];
      this.state.forEach((row, rindex) => {
        row.forEach((cell, cindex) => {
          if (cell !== 0 && rindex !== 11) {
            pos.push([rindex, cindex]);
          }
        });
      });

      pos.forEach((p) => {
        const row = p[0];
        const column = p[1];
        this.state[row][column] = 0;
        this.state[row + 1][column] = 1;
      });
      console.log(this.state);
    }
  },
  data () {
    return {
      state: [
        [1,0,0,0,0,0],
        [0,0,0,0,0,0],
        [0,0,0,0,0,0],
        [0,0,0,0,0,0],
        [0,0,0,0,0,0],
        [0,0,0,0,0,0],
        [0,0,0,0,0,0],
        [0,0,0,0,0,0],
        [0,0,0,0,0,0],
        [0,0,0,0,0,0],
        [0,0,0,0,0,0],
        [0,0,0,0,0,0]
      ]
    }
  }
}
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
.main-field {
  height: 100%;
  display: flex;
}
.left-field {
  width: 50%;
}
.ojama-field {
  height: 20%;
  background-color: gray;
}
.play-field {
  background-color: lightgrey;
  height: 80%;
  display: flex;
  flex-direction: column;
}

.play-field > div {
  display: flex;
  flex-grow: 1;
}

.play-field > div > div {
  flex-grow: 1;
}

.play-field div {
  border: solid 1px black;
}

.red {
  background-color: chartreuse;
}

.next-field {
  border: solid 1px black;
  height: 25%;
  width: 50%;
}

</style>
