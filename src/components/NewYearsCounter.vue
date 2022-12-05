<template>
  <div class="counter">
   <h1>New Years Day</h1>
   <h2>Countdown to the year 2023</h2>
    <div class="container">
      <div class="item">
        <p class="number">{{ days }}</p>
        <p class="text">days</p>
      </div>
      <div class="item">
        <p class="number">{{ hours % 24 }}</p> 
        <p class="text">hours</p>
      </div>
      <div class="item">
        <p class="number">{{ minutes % 60 }}</p> 
        <p class="text">minutes</p>
      </div>
      <div class="item">
        <p class="number">{{seconds % 60 }}</p>
        <p class="text">seconds</p>
      </div>
    </div>

  </div>
</template>

<script>
import { ref} from 'vue';

export default {
  name: 'NewYearsCounter',
  setup() {
    
    const newYearDay = new Date('01/01/2023');
    const now = new Date();
    const days = ref(0);
    const hours = ref(0);
    const minutes = ref(0);
    const seconds = ref(0);
  
    
    setInterval(() => {  
      const currentTime = new Date();       
      const delta =newYearDay - currentTime;     
      seconds.value = parseInt(delta / 1000)
      console.log(seconds.value)
      minutes.value = parseInt(seconds.value / 60 );
      hours.value = parseInt(minutes.value / 60);
      days.value = parseInt(hours.value / 24);
     

    }, 1000)  

    return {newYearDay, now, days, hours, minutes, seconds}
  }
}
  
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;800&display=swap');
.counter { 
  background-image: url('../assets/ian-schneider-PAykYb-8Er8-unsplash.jpg');
  background-color: rgba(255, 255, 255, 0.9);
  background-repeat: no-repeat;
  background-position: center center;
  background-size: cover;
  text-align: center;
  height: 100vh;
  width: 100vw;
  overflow: hidden;
  margin: 0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  color: white;  
  font-family: 'Poppins', sans-serif;
}
h1 {
  font-size: 4em;
  letter-spacing: 3px;
  text-transform: uppercase;
}
h2 {
  font-size: 3em;
  letter-spacing: 2px;
  text-transform: uppercase;
}
  .container {
    display: flex;
    flex-wrap: wrap;
    width: 100vh;
    margin-inline: auto;
    justify-content: space-evenly;
    align-items: center;
    column-gap: 1rem;
    height: auto;
    margin-top: 3rem;
    
  }
  .item {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 100%;
    color: white;
    
  }
  .number {
    display: inline-flex;
    font-size: 10em;   
    margin:0;    
    display: flex;
    justify-content: center;
    align-items: center;
    width: 110px;
    height: 110px;

  }
  .text {
    font-size: 2rem;
    font-weight: 800;
    text-transform: uppercase;
  }
</style>
