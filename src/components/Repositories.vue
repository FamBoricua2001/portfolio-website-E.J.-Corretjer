<template>
    <div class="repositories">
      <h2>My GitHub Repositories</h2>
      <ul>
        <li v-for="repo in repositories" :key="repo.id">
          <a :href="repo.html_url" target="_blank">portfolio-website-E.J.-Corretjer</a>
          <p>{{ repo.description }}</p>
          <p><strong>Language:</strong> {{ repo.language }}</p>
          <p><strong>Last Updated:</strong> {{ new Date(repo.updated_at).toLocaleDateString() }}</p>
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
        loading: true,
        error: null
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
          this.error = 'Error fetching repositories';
          console.error('Error fetching repositories:', error);
        } finally {
          this.loading = false;
        }
      }
    }
  };
  </script>
  
  <style scoped>
  
  </style>
  