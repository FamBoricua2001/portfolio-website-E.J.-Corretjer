<template>
    <div class="repositories">
        <h1>GitHub Repositories</h1>
        <div v-if="loading" class="loading">Loading....</div>
        <ul v-if="!loading">
            <li v-for="repo in repositories" :key="repo.id">
                <a :href="repo.html_url">FamBoricua2001</a>
                <p>This is a compulation of projects that have been worked on myself.</p>
                <p><strong>Language:</strong>{{repo.language}}</p>
                <p><strong>Last Updated:</strong>{{new Date(repo.updated_at).toLocaleDateString()}}</p>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
  name: 'Repositories',
  data() {
    return {
      repositories: []
    };
  },
  created() {
    this.fetchRepositories();
  },
  methods: {
    async fetchRepositories() {
      try {
        const response = await fetch('https://api.github.com/users/FamBoricua2001/repos');
        const data = await response.json();
        this.repositories = data;
      } catch (error) {
        console.error('Error fetching repositories:', error);
      }
    }
  }
};
</script>

<style scoped>
.loading {
  text-align: center;
  font-size: 20px;
  color: gray
}
</style>