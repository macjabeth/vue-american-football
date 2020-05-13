<template>
  <div id="app">
    <Scoreboard :score="score" :time="time" />
    <Controls :incrementScore="incrementScore" />
  </div>
</template>

<script>
  import Scoreboard from '@/components/Scoreboard';
  import Controls from '@/components/Controls';

  export default {
    name: 'App',
    components: { Controls, Scoreboard },
    mounted() {
      this.timer = this.$nextTick(() => {
        setInterval(this.incrementTime, 1000);
      });
    },
    destroyed() {
      clearInterval(this.timer);
    },
    data() {
      return {
        score: { home: 32, guest: 3 },
        time: { minute: 0, second: 3 }
      };
    },
    methods: {
      incrementScore(team, amount) {
        this.score[team] += amount;
      },
      incrementTime() {
        if (++this.time.second === 60) {
          this.time.second = 0;
          this.time.minute++;
        }
      }
    }
  };
</script>

<style>
  @import "preflight.css";

  body {
    background-color: black;
    color: #F6F6F6;
    font-family: monospace;
  }

  #app {
    align-items: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
    min-height: 100vh;
  }
</style>
