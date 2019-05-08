<template>
  <div>
    <div class="timerContainer">
      <div class="timerDiskHole"></div>
      <div class="timerDisk"></div>
      <div class="timerGroundEnd"></div>
      <div class="timerBarEnd"></div>
      <div class="timerBarKnob"></div>
      <div v-if="timerType == 'countdown'">
        true
        <div class="count_down timerDirection"></div>
      </div>
      <div v-else>
        false
        <div id="timerDirection"></div>
      </div>
      <div class="timerTime"></div>
    </div>
    <button type="button" class="btn btn-primary" autocomplate="off" data-loading-text="jquery with bootstrap" @click="clickBtn"> Hello</button>
  </div>
</template>

<script>
const DURATION_IN_SECONDS = 60 * 60
import $ from 'jquery'
import ProgressBar from 'progressbar.js'

export default {
  name: 'HelloWorld',
  mounted : ()=>{
  },
  created : ()=>{
  },
  data : function () {
    return {
	  duration : DURATION_IN_SECONDS,
	  timerType : "countdown",	
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
	},
	toggleTimerType (event) {
		
	}
	

	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.timerContainer {
  position: relative;
  width: 80vmin;
  height: 80vmin;
  margin: auto;
  margin-top: 10vh;
  color: #8e8d8d;
  border-radius: 50%;
}

.timerDisk {
  border-radius: 50%;
  box-shadow: 0px 0px 20px 20px hsl(0, 0%, 10%);
  border-width: 5px;
  border-style: solid;
  border-color: hsl(0, 0%, 16%);
}

.timerDiskHole {
  display: inline-block;
  position: absolute;
  width: 20%;
  height: 20%;
  left: 40%;
  top: 40%;
  border-radius: 50%;
  box-shadow: inset 0px 0px 20px 5px rgba(0,0,0,0.5);
  border-style: solid;
  border-color: rgb(40, 40, 40);
  border-width: 5px;
}

.timerDisk > svg > path:nth-child(1) {
 stroke: #2c333f;
}

.timerGroundEnd {
  position: absolute;
  width: 100px;
  height: calc(40% + 5px);
  top: 0px;
  left: 50%;
  background: #292929;
  box-shadow: -15px 3px 20px 1px rgba(0,0,0,0.5);
  clip: rect(-53px 6px 1000 -1000px);
}

.timerBarEnd {
  position: absolute;
  width: 8px;
  height: 39%;
  background: #292929;
}

.timerBarKnob {
  position: absolute;
  height: 32px;
  width: 32px;
  background-color: #b3b3b3;
  border-radius: 50%;
  cursor: pointer;
  box-shadow: 0px 4px 16px 0px rgba(0,0,0,0.75), 0px 0px 8px 0px rgba(0,0,0,0.4) inset;
}

.timerTime {
  display: inline-block;
  position: absolute;
  width: 20%;
  height: 20%;
  left: 40%;
  top: 40%;
  padding-top: 8%;
  text-align: center;
  font-family: 'Helvetica';
  font-size: 4.5vmin;
  border-radius: 50%;
  cursor: pointer;
}

.timerDirection {
  position: absolute;
  width: 3%;
  height: 3%;
  left: calc(50% - 1.5%);
  top: calc(40% - -3.5%);
  background-image: url("../../public/count_down.png");
  background-size: contain;
  background-repeat: no-repeat;
}

.count_down {
  background-image: url("../../public/count_down.png");
}

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
