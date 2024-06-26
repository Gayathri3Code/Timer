<template>
    <div class="timer">
      <h1>{{ formattedTime }}</h1>
      <button @click="startTimer">Start</button>
      <button @click="stopTimer">Stop</button>
      <button @click="resetTimer">Reset</button>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        time: 0,
        interval: null
      };
    },
    computed: {
      formattedTime() {
        const minutes = Math.floor(this.time / 60).toString().padStart(2, '0');
        const seconds = (this.time % 60).toString().padStart(2, '0');
        return `${minutes}:${seconds}`;
      }
    },
    methods: {
      startTimer() {
        if (this.interval) return;
        this.interval = setInterval(() => {
          this.time++;
        }, 1000);
      },
      stopTimer() {
        clearInterval(this.interval);
        this.interval = null;
      },
      resetTimer() {
        this.stopTimer();
        this.time = 0;
      }
    },
    beforeDestroy() {
      this.stopTimer();
    }
  };
  </script>
  
  <style scoped>
  .timer {
    text-align: center;
    margin: 20px;
  }
  button {
    margin: 5px;
    padding: 10px;
    background-color: #40215a;
    color: white;
    border: none;
    cursor: pointer;
    border-radius: 5px;
    transition: box-shadow 0.3s ease;
    margin-bottom:8%;
}
button:hover {
  background-color: #3a0f46;
  box-shadow: 0px 4px 8px rgba(243, 242, 242, 0.3);
}
@media (max-width: 600px) {
  h1 {
    font-size: 2.5rem;
  }

  button {
    padding: 10px 15px;
    font-size: 1rem;
  }
}
  </style>
  