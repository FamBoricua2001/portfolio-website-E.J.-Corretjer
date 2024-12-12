<template>
    <div class="repositories">
        <h1>My GitHub Repositories</h1>
        <ul>
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

</style>