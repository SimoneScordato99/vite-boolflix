<script >
export default {
    name:'Film',
    props:['propsFilmNome']
}
</script>

<template>
    <div class="card">
    <div class="card-body">
      <h5 class="card-title">{{ propsFilmNome.original_title }}</h5>
      <p class="card-text">{{ propsFilmNome.title }}</p>
      <p class="card-text">{{ propsFilmNome.original_language }}</p>
      <p class="card-text">{{ propsFilmNome.vote_average }}</p>
      
  </div>
</div>
</template>

<style scoped lang="scss">

</style>