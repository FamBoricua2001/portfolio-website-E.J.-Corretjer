<template>
    <div class="repositories">
      <h2>GitHub Repositories</h2>
      <a :href="'https://github.com/$FamBoricua2001'" target="_blank">FamBoriuca2001</a>
      <div class="projects-container">
        <ul class="project-list">
         <li v-for="repo in repositories" :key="repo.id" class="project-item">
            <div class="project">
             <p style="color: red;"><strong>Project Name:</strong> {{ repo.description }}</p>
             <p style="color: red;"><strong>Language:</strong> {{ repo.language }}</p>
             <p style="color: red;"><strong>Last Updated:</strong> {{ new Date(repo.updated_at).toLocaleDateString() }}</p>
            </div>
          </li>
        </ul>
      </div>
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
    color: black;
    text-align: center;
  }

  p {
    color: gray
  }
  
  a {
    color:blue;
  }
  
  a:hover {
    color:red
  }
  
  .repositories {
    max-width: 800px;
    margin: 0 auto;
    padding: 20px;
  }
  
  .projects-container {
    display: grid;
    flex-wrap: wrap;
  }

  .projects-list {
    display: grid;
    flex-wrap: wrap;
    padding: 0;
    margin: 0;
    list-style-type: none;
  }

  .project-item {
    grid: 1 0 45%;
    margin: 10px;
  }

  .project {
    padding: 15px;
    border: 1px solid black;
    border-radius: 5px;
    box-shadow: 0 2px 4px rba(0, 0, 0, 0.1);
  }

  .loading {
    text-align: center;
    font-size: 20px;
    color: gray
  }
  
  .error {
    text-align: center;
    font-size: 20px;
    color: red
  }
  
  ul {
    list-style-type: none;
    padding: 0;
  }

  .repo.description {
    font-size: 14px;
    color: black;
  }
  
  strong {
    color: black;
  }

  .custom-color {
    color: red;
  }
  </style>