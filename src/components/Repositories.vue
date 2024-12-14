<template>
    <div class="repositories">
      <ul>
        <li v-for="repo in repositories" :key="repo.id">
          <h2>GitHub Repositories</h2>
          <a :href="repo.html_url" target="_blank">FamBoriuca2001</a>
          <p>{{ repo.description }}</p>
          <p><strong>Language:</strong>{{ repo.language }} </p>
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
  h2 {
    text-align: center;
  }

  .repositories ul {
    text-align: center;
  }

  .repositories li {
    text-align: center;
  }

  .repo-link {
    font-size: 2px;
    color: purple
  }
  </style>
  