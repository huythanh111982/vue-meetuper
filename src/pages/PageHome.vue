<template>
<div>
  <AppHero />
  <div class="container">
    <section class="section">
      <div class="m-b-lg box-title">
        <h1 class="title is-inline">Featured Meetups in "Location"</h1>
        <AppDropdown />
        <button class="button is-primary is-pulled-right m-r-sm">
          Create Meetups
        </button>
        <router-link :to="{name:'PageMeetupFind'}" class="button is-primary is-pulled-right m-r-sm">All</router-link>
      </div>
      <div class="row columns is-multiline">
        <!-- Start Meetuper -->
        <MeetupItem v-for="meetup in meetups"
                    :key="meetup._id"
                    :meetup="meetup" />
        <!-- End Meetuper -->
      </div>
    </section>
    <section class="section">
      <div>
        <h1 class="title">Categories</h1>
        <div class="columns cover is-multiline is-mobile">
          <!-- Categories -->
          <category-item v-for="category in categories" :key="category._id" :category="category" />
        </div>
      </div>
    </section>
  </div>
</div>
</template>

<script>
import axios from "axios";
import CategoryItem from "../components/CategoryItem.vue";
import MeetupItem from '@/components/MeetupItem'
export default {
  components: {
    CategoryItem,
    MeetupItem
  },
  data() {
    return {
      categories: [],
      meetups: [],
    };
  },
  created() {
    // Get data Meetuper
    axios.get("/api/v1/meetups").then((res) => (this.meetups = res.data));
    // Get data Category
    axios.get("/api/v1/categories").then((res) => {
      this.categories = res.data;
    });
  },
};
</script>

<style scoped>
button{
  margin-right: 5px;
}
.box-title{
  margin-bottom: 15px;
}
.box-title::after {
  content: "";
  clear: both;
  display: table;
}
</style>
