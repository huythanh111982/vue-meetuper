<template>
  <div class="notFoundContainer">
      <div class="m-b-xxl">
        <h1 class="title">{{title}}</h1>
        <router-link :to="{name: navigateToPage}" class="button is-primary">{{navigaToText}}</router-link>
      </div>
      <h2 class="subtitle">{{status}}<span> :(</span></h2>
    </div>
</template>

<script>
  export default {
    props: {
     title: {
       type: String,
       reuired:true 
     },
     status: {
       type: String,
       reuired:true 
     },
     navigateToPage: {
       type: String,
       reuired:true 
     },
     navigaToText: {
       type: String,
       reuired:true 
     },
   },
  }
</script>

<style lang="scss" scoped>

</style>