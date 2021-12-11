<template>
<div>
    <div class="chart-set">
        <h1>Temparature Variation</h1>
        <div  class="linechart"> <LineChart :width="200" :height="300" /> </div>
    </div>
</div>
</template>


<script>
import LineChart from './LineChart.vue'
 export default {
    name:'TempChart',
    props: ['tempVar','tempVarDt'],
    components: {LineChart},
  }
</script>


<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

.linechart{

    height:200px;
}

body:scoped {
    font-family: 'montserrat', sans-serif;
   
}

.chart-set {
    border: 1px solid green;
    display: inline-block;
    height: 50vh;
    width: 70%;
    float: left;
    margin-top:30px;
    margin-left: 30px;
}
</style>
