<template>
<div>
    <div class="temp-variation">
        <h1>Temparature Hightlight</h1>
        <div class="card-wrapper">
            <div class="card">
                <h2>UV Index</h2>
                <img src="../assets/uv-index.png" />
                <h3>{{uvi}}</h3>
            </div>

            <div class="card">
                <h2>Visibility</h2>
                <img src="../assets/visibility.png" />
                <h3>{{visible}}</h3>
            </div>

            <div class="card">
                <h2>Wind Status</h2>
                <div class="card-wrapper-wind">
                <div>
                <h5>Wind Speed</h5>
                <img src="../assets/wind_speed.png" />
                <p>{{speed}}</p>
                
                
                </div>
                <div>
                <h5>Wind Degree</h5>
                <img src="../assets/wind_degree.png" />
                <p>{{degree}}degree</p>
                </div>
                </div>

            </div>
        </div>
    </div>

</div>
</template>

<script>
export default {
    name: 'TempHighlight',
    props:['speed','uvi','degree','visible'],
    
}

</script>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

div h1, h2 scoped{
    background-color: gray
}

div h3{
   
}

body {
    font-family: 'montserrat', sans-serif;
}

.temp-variation {

    border: 1px solid green;
    height: 36vh;
    width: 70%;
    float: left;
    margin-top: 30px;
    margin-left: 30px;
}

.temp-variation .card-wrapper {
    justify-content: center;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-gap: 150 px;
    margin: 40px 15px;

}
.card-wrapper-wind {
    justify-content: center;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-gap: 150 px;
    margin: 20px 15px;

}



.temp-variation .card-wrapper .card {
    border: 1px solid black;
    height:150px;
}
</style>
