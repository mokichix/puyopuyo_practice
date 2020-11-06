<template>
<div class="main-field">
  <div class="left-field">
    <div class="ojama-field">
    </div>
    <div class="play-field">
      <table class="play-field-table">
        <tr><td></td><td></td><td></td><td></td><td></td><td></td></tr>
      </table>
    </div>
  </div>
  <div class="next-field">
  </div>
</div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
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
}
.play-field-table > tr > td {
  border: solid 5px black;
  border-color: black;
  width: 18%;
  height: 8.333%;
}
.next-field {
  border: solid 1px black;
  height: 25%;
  width: 50%;
}

</style>
