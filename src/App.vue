<script>
export default {
  data() {
    return {
      currentBranch: "main"
    }
  }
}
</script>

<template>
  <div class="container">
    <h1 class="heading">Latest Vue Core Commits</h1>
    <div class="radio-container">
      <div class="radio-input">
        <input type="radio" id="main" value="main" v-model="currentBranch">
        <label for="main">Main</label>
      </div>
      <div class="radio-input">
        <input type="radio" id="v2-compat" value="v2-compat" v-model="currentBranch">
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
  gap: 0.5rem;
}

.radio-input {
  padding: 1rem;
  display: flex;
  gap: 0.3rem;
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
