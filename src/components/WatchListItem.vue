<template>
  <!-- <div> -->
    <div @click="CheckMovie">
    <p :class="{ 'is-completed': movie.isselected }">{{movie.title}}</p>
    </div>
  <!-- </div> -->
</template>

<script>
export default {
  name: 'WatchListItem',
  props: {
    movie: Object
  },
  methods: {
    CheckMovie() {
      this.$store.commit('CHANGESELECT', this.movie)
    }
  }
}
</script>

<style>
  .is-completed {
    text-decoration: 2px line-through #42b983;
  }
</style>