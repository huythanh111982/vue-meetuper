<template>
  <div
    class="column is-one-quarter"
    :style="{ 'min-height': '160px' }"
  >
    <a href="#">
      <span class="is-primary is-top is-medium tooltip">
        <figure class="image is-4by3 imageFade">
          <img class="is-rounded" :src="category.image" />
        </figure>
        <div class="subtitle m-t-xs bold">{{ category.name  | captilize}}</div>
      </span>
    </a>
  </div>
</template>

<script>
export default {
  props: {
    category: {
      type: Object,
      required:true
    },
  },
};
</script>

<style lang="scss" scoped>
.is-rounded {
  border-radius: 10px !important;
}
</style>
