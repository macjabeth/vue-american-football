<template>
  <div class="border">
    <div class="scoreboard">
      <div class="row">
        <div>
          <h2>Home</h2>
          <div class="score">{{homeScore}}</div>
        </div>
        <div class="time">
          <span class="score">{{currentMinute}}</span>
          <span>:</span>
          <span class="score">{{currentSecond}}</span>
        </div>
        <div>
          <h2>Guest</h2>
          <div class="score">{{guestScore}}</div>
        </div>
      </div>
      <div class="row">
        <div>
          <h2>Down</h2>
          <div class="score">4</div>
        </div>
        <div>
          <h2>To Go</h2>
          <div class="score">15</div>
        </div>
        <div>
          <h2>Ball On</h2>
          <div class="score">21</div>
        </div>
        <div>
          <h2>QTR</h2>
          <div class="score">4</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Scoreboard',
    props: {
      score: Object,
      time: Object
    },
    computed: {
      currentMinute() {
        return this.time.minute.toString().padStart(2, '0');
      },
      currentSecond() {
        return this.time.second.toString().padStart(2, '0');
      },
      homeScore() {
        return this.score.home.toString().padStart(2, '0');
      },
      guestScore() {
        return this.score.guest.toString().padStart(2, '0');
      }
    }
  };
</script>

<style scoped>
  .border {
    width: 800px;
    max-width: 95%;
    padding: .5rem;
  }

  .border, .scoreboard {
    background-color: #272727;
    border-radius: 10px;
  }

  .scoreboard {
    border: 5px solid #FCFCFC;
    padding: 1.5rem;
  }

  .row {
    align-items: center;
    display: flex;
    justify-content: space-between;
  }

  .row:first-of-type {
    margin-bottom: 1rem;
  }

  .row > div {
    align-items: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 0 2rem;
  }

  .row h2 {
    font-size: 2rem;
    text-transform: uppercase;
  }

  .score {
    color: #F8492A;
    font-size: 5rem;
  }

  .time {
    border: 5px solid #FCFCFC;
    border-radius: 10px;
    flex-direction: row !important;
    padding: 0 2.5rem;
  }

  .time span:not(.score) {
    font-size: 5rem;
    margin-top: -1rem;
  }
</style>