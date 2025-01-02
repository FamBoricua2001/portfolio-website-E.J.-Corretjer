<template>
    <div class="repositories">
      <h2>GitHub Repositories</h2>
        <div v-if="loading" class="loading">Loading....</div>
        <div v-if="error" class="error">{{ error }}</div>
        <ul v-if="!loading && !error">
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
import axios from 'axios';

export default {
  name: 'Repositories',
  data() {
    return {
      repositories: [],
      loading:true,
      error:null
    };
  },
  created() {
    this.fetchRepositories();
  },
  methods: {
    async fetchRepositories() {
      try {
        const response = await axios.get('https://api.github.com/users/FamBoricua2001/repos');
        this.repositories = response.data;
      } catch (error) {
        console.error('Error fetching repositories:', error);
        this.error = 'Error fetching repositories';
      } finally {
        this.loading=false;
      }
    }
  }
};
</script>

<style scoped>

</style>