<template>
  <h1>{{ title }}</h1>
  
  <div  class="Game">
    </div>
    <button class="Reset" @click="Reset">Reset</button>
  
  
  </template>
  
  <script>
  const imagePaths = ["images/car.jpg" ,
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
        "images/Whale.jpg"];
  
    const imagesArray = imagePaths.map(path => {
    const img = new Image();
    img.src = path;
    img.alt = `Obiekt ${path}`; 
    return img;
  });
  
  
  
  export default {
    data() {
   return{
    title:'Memory Game',
    imagesArray: imagesArray,
      }
    },
    methods: {
      Reset() {
        window.location.reload();
      },
    },
    mounted() {
    var shuf_cards = imagesArray.sort(() => (Math.random() > 0.5) ? 2 : -1);
    for (var i = 0; i < imagesArray.length; i++) {
      let box = document.createElement('div');
      box.className = 'item';

      let img = document.createElement('img');
      img.src = shuf_cards[i].src;
      img.alt = shuf_cards[i].alt;
      box.appendChild(img);

      box.onclick = function () {

        this.classList.toggle('boxOpen')
        setTimeout(function () {
  if (document.querySelectorAll('.boxOpen').length > 1) {
    if (
      document.querySelectorAll('.boxOpen')[0].innerHTML ===
      document.querySelectorAll('.boxOpen')[1].innerHTML
    ) {
      document.querySelectorAll('.boxOpen')[0].classList.add('boxMatch');
      document.querySelectorAll('.boxOpen')[1].classList.add('boxMatch');
      document.querySelectorAll('.boxOpen')[1].classList.remove('boxOpen');
      document.querySelectorAll('.boxOpen')[0].classList.remove('boxOpen');

      if (
        document.querySelectorAll('.boxMatch').length === imagesArray.length
      ) {
        alert('win');
      }
    } else {
      document.querySelectorAll('.boxOpen')[1].classList.remove('boxOpen');
      document.querySelectorAll('.boxOpen')[0].classList.remove('boxOpen');
    }
  }
}, 1500);


      }
      document.querySelector('.Game').appendChild(box);
    }
  },
};
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
    background-color: #a89f24;
  }
  
  #app{
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    gap: 15px;
    background: #d2c72e;
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
    color: #ffff00;
    background: #FBB;
    border: none;
    font-size: 1.5em;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    cursor: pointer;
    font-weight: 600;
    border-radius: 15px;
  }
  
  .Reset:focus{
    background-color:  #fff;
    font-weight: 500;
  }
  
  .Game {
   gap: 15px;
   display: flex;
   flex-wrap: wrap;
   transform-style: preserve-3d;
   perspective: 500px;
   width: 740px;
  }
  
  .item {
    width: 170px;
    height: 170px;
    position: relative;
    display: flex;
    justify-content: center;
    background-color: #fff;
    transition: 0.3s;
    transform: rotateY(180deg);
  }
  
  
  
  .item::after {
    content: '';
    position: absolute;
    inset: 0;
    background: #ffff00;
    transition: rotateY(0deg);
    backface-visibility: hidden;
    /* opacity: 0.5; */
  }
  
  .item.boxOpen{
    transform: rotateY(0deg);
  }
  

  .boxMatch:after,
  .boxOpen::after{
    transform: rotateY(180deg)
  }
  </style>
  