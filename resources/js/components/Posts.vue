<template>
  <main>
    <div class="container">
      <h1>Elenco post:</h1>
    </div>
  </main>
</template>

<script>
export default {
  name: 'Posts',

  data(){
    return {
      apiUrl: 'http://127.0.0.1:8000/api/posts',
      posts: null
    }
  },
  
  mounted(){
    this.getPosts();
  },

  methods: {
    getPosts(){
      axios.get(this.apiUrl)
      .then( res => {
        this.posts = res.data;
        console.log(this.posts);
      })
    }
  }
}
</script>

<style lang="scss" scoped>
  main{
    padding: 20px 0;
  }
</style>