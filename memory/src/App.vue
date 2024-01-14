<template>
<h1>{{ title }}</h1>

<div class="Game">

</div>

<button @click="Play">
  Play!
</button>

<button @click="Reset">
  Reset
</button>

<div class="Timer">
  Time:
</div>

       Name Time
Ranking: 
</template>

<script>


export default {
  data() {
 return{
  title:'Memory Game'
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

</style>
