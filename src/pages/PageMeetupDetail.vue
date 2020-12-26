<template>
  <div>
    <h1>This is component Meetup Detail</h1>
  </div>
</template>

<script>
  export default {
    created () {
      debugger
      this.$route.params.id;
    },
  }
</script>

<style lang="scss" scoped>

</style>