<template>
  <article>
    <h3>
      <a href="#">{{post.title}}</a>
    </h3>
    <p class="date" >{{formatData}}</p>
    <p class="text">{{troncateText}}</p>
  </article>
</template>

<script>
export default {
  name: 'PostItem',
  props: {
    'post': Object
  },
  computed: {
    troncateText(){
      return this.post.content.substr(0, 50) + '...';
    },
    formatData(){
      const d = new Date(this.post.created_at);
      let day = d.getDay();
      let month = d.getMonth() +1;
      const year = d.getFullYear();

      if(day < 10){
        day = '0' + day;
      }

      if(month < 10){
        month = '0' + month;
      }

      console.log(month);
      return `${day}/${month}/${year}`;
    }
  }
}
</script>

<style lang="scss" scoped>
  article {
    padding: 10px 0;
    a {
      color: black;
      text-decoration: none;
      &:hover {
        text-decoration: underline;
      }
    }
    .date {
      font-size: 12px;
      font-style: italic;
    }
    
  }
</style>