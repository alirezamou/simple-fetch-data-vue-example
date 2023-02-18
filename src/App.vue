<script>
</script>

<template>
  <div class="container">
    <h1 class="heading">Latest Vue Core Commits</h1>
    <div class="radio-container">
      <div class="radio-input">
        <input type="radio" id="main">
        <label for="main">Main</label>
      </div>
      <div class="radio-input">
        <input type="radio" id="v2-compat">
        <label for="v2-compat">V2-compat</label>
      </div>
    </div>
    <div class="commits-container">
      <p>vuejs/vue@main</p>
      <ul>
        <li>commit 1</li>
        <li>commit 1</li>
      </ul>
    </div>
  </div>
</template>

<style scoped>
.radio-container {
  display: flex;
}

.radio-input {
  padding: 1rem;
}

.commits-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: start;
  gap: 0.5rem;
}

.container {
  max-width: 50vw;
  padding: 0.5rem;
}

.heading {
  font-weight: bold;
}

</style>
