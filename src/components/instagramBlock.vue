<template>
  <div class="instagram-block">
    <div class="instagram-block-icon">
      <img class="instagram-block-icon-image" :src="resolve_img_url('insta.svg')">
    </div>
    <div class="instagram-block-description">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: 'instagram-block',
  methods: {
    resolve_img_url(path) {
      let images = require.context('../assets/images', false)
      return images("./" + path)
    }
  }
}
</script>

<style scoped>
  .instagram-block {
    display: inline-flex;
    align-items: center;
  }

  .instagram-block-icon {
    width: 60px;
    height: 60px
  }

  .instagram-block-icon-image {
    width: 100%;
    height: 100%
  }

  .instagram-block-description {
    font-family: 'Bebas Neue';
    font-weight: 400;
    font-size: 28px;
    margin-top: 2px;
    margin-left: -8px
  }
</style>
