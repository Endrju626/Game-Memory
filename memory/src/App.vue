<template>
<h1>{{ title }}</h1>

<div v-for="(image, index) in images" :key="index" class="Game">
<img :src="image" alt="memory pic" width="256px" height="256px"/>

</div>

<button class="Play" @click="Play">
  Play!
</button>

<button class="Reset" @click="Reset">
  Reset
</button>

<div class="Timer">
  Time:
</div>

       Name Time
Ranking: 
<!-- <img src="../../Images/car.jpg"> -->
</template>

<script>


export default {
  data() {
 return{
  title:'Memory Game',
  images:[
      "images/car.jpg" ,
      "images/car.jpg",
      "images/Chameleon.jpg",
      "images/Chameleon.jpg",
      "images/Eclipse.png",
      "images/Eclipse.png",
      "images/Microscope.jpg",
      "images/Microscope.jpg",
      "images/Nebula.jpg",
      "images/Nebula.jpg",
      "images/Pyramid.png",
      "images/Pyramid.png",
      "images/Sun.jpg",
      "images/Sun.jpg",
      "images/Whale.jpg",
      "images/Whale.jpg"
  ]
    }
  },
  methods: {
    Play(){
      alert('start')
    },
    Reset(){
      alert('no')
    }
  }
}
</script>

<style>
*
{
margin: 0;
padding: 0;
box-sizing: border-box;
font-family: monospace;
}
body
{
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background-color: #0a3c2f;
}

#app{
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  gap: 15px;
  background: #0d614b;
  padding: 40px 60px;
}

h2{
  font-size: 3em;
  color: #fff;
  text-transform: uppercase;
  letter-spacing: 0.1em;
}

.Reset{
  padding: 15px 20px;
  color: #267c65;
  background: #fff;
  border: none;
  font-size: 1.5em;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  cursor: pointer;
  font-weight: 600;
}

.Reset:focus{
  background-color:  #fff;
  font-weight: 500;

}

.Game {
 gap: 15px;
}


</style>
