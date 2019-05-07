<template>
  <div>
    <div id="timerContainer">
      <div id="timerDiskHole"></div>
      <div id="timerDisk"></div>
      <div id="timerGroundEnd"></div>
      <div id="timerBarEnd"></div>
      <div id="timerBarKnob"></div>
      <div id="timerDirection"></div>
      <div id="timerTime"></div>
    </div>
    <button type="button" class="btn btn-primary" autocomplate="off" data-loading-text="jquery with bootstrap" @click="clickBtn"> Hello</button>
    {{ duration }}
  </div>
</template>

<script>
const DURATION_IN_SECONDS = 60 * 60
import $ from 'jquery'

export default {
  name: 'HelloWorld',
  data : function () {
    return {
      duration : DURATION_IN_SECONDS
    }
  }
  ,
  props: {
    
  },
  methods: {
    clickBtn (event) {
      $(event.target).button('loading')

      setTimeout(function() {
        $(event.target).button('reset')
      }, 1000);
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
</style>
