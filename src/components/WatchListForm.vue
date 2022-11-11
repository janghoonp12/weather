<template>
  <div>
    <input type="text" v-model.trim="InputText" @keyup.enter="PushMovies">
    <input type="submit" @click.enter="PushMovies" value='Add'>
    <br>
    <br>

  </div>
</template>

<script>
export default {
  name: 'WatchListForm',
  data() {
    return {
      InputText: null
    }
  },
  methods: {
    PushMovies() {
      if (this.InputText) {
        this.$store.dispatch('PushMovies', this.InputText)
        this.InputText = null
      }
      else {
        this.InputText = null
        alert('영화를 입력해주세요!')
      }
    }
  },
}
</script>

<style>

</style>