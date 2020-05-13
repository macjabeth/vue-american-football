<template>
  <div class="controls">
    <div>
      <span>Home:</span>
      <button @click="incrementScore('home', 7)">Touchdown</button>
      <button @click="incrementScore('home', 3)">Field Goal</button>
    </div>
    <div>
      <span>Guest: </span>
      <button @click="incrementScore('guest', 7)">Touchdown</button>
      <button @click="incrementScore('guest', 3)">Field Goal</button>
    </div>
  </div>
</template>
<script>
  export default {
    name: 'Controls',
    props: ['incrementScore']
  };
</script>
<style scoped>
  .controls, .controls > div {
    display: flex;
  }

  .controls > div {
    align-items: center;
  }

  .controls {
    width: 800px;
    max-width: 90%;
    justify-content: space-around;
    margin-top: 1rem;
  }

  button {
    border: 1px solid;
    padding: .5em 1em;
    margin: 5px;
    border-radius: 5px;
  }
  button:hover {
    color: #F8492A;
  }
  button:focus {
    outline: none;
  }
</style>