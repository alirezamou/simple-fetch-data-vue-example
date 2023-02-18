<script>
const BASE_API_URL = "https://api.github.com/repos/vuejs/core/commits?per_page=3&sha=";
export default {
  data() {
    return {
      currentBranch: "main",
      commits: null
    }
  },
  created() {
    this.fetchData();
  },
  methods: {
    fetchData () {
      const url = `${BASE_API_URL}${this.currentBranch}`;
      fetch(url)
      .then(res => res.json())
      .then(data => this.commits = data)
      .catch(err => console.log(err));
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
      <p>vuejs/vue@{{ currentBranch }}</p>
      <ul>
        <li class="commit" v-for="{ sha, html_url, commit } in commits">
          <a target="_blank" class="commit__link" :href="html_url">{{ sha.slice(0, 7) }}</a> - <span>{{ commit?.message }}</span>
          <br />
          <a target="_blank" class="author" :href="commit?.author?.email">{{ commit?.author?.name }}</a>
        </li>
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

.commit {
  margin-bottom: 1rem;
}

.commit__link, .author {
  text-decoration: none;
  color: cyan;
}

.commit__link:visited, .author:visited {
  color: purple;
}

.commit__link:hover, .author:hover {
  color: blue;
}

.commit__link:visited:hover, .author:visited:hover {
  color: purple;
}

</style>
