<template>
	<section>
    <h1>User Page</h1>

    <hr>

    <h2>{{user.name}}</h2>

    <p>{{user.email}}</p>
  </section>
</template>

<script>
  export default {
    name: "_id",
    validate({params}) {
      return /^\d+$/.test(params.id)
    },
    async asyncData({$axios, params}) {
      const user = await $axios.$get('https://jsonplaceholder.typicode.com/users/' + params.id)
      return {user}
    },
  }
</script>

<style scoped>

</style>
