<template>
  <div class="home">
    <button class="btn btn-primary" @click="goToDayBook">Go to Daybook</button>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'HomeView',
  methods: {
      goToDayBook () {
        this.$router.push({name:"no-entry"})
      }
  }

}
</script>
