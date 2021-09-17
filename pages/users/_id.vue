<template>
  <h1>ユーザーID： {{ user.name }}</h1>
</template>
<script>
export default {
  head() {
    return {
      title: `${this.user.name}のページ`,
    }
  },
  data() {
    return {
      id: this.$route.params.id,
      users: [
        { id: 1, name: 'John Doe'},
        { id: 2, name: 'Kevin Smith'},
        { id: 3, name: 'Harry Bosch'},
        { id: 4, name: 'Merry Jean'},
      ]
    }
  },
  computed: {
    user() {
      return this.users.find(user => user.id == this.id);
    }
  },
  mounted: function() {
    console.log(this.$route)
  },
  created: function(){
    console.log(this.$route)
  }
}
</script>
