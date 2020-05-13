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
    justify-content: space-around;
    margin-top: 1rem;
    max-width: 90%;
    width: 800px;
  }

  button {
    border: 1px solid;
    border-radius: 5px;
    margin: 5px;
    padding: .5em 1em;
  }

  button:hover {
    color: #F8492A;
  }

  button:focus {
    outline: none;
  }
</style>