<template>
  <div>
    <div class="block-head">
      <slot name="header"></slot>
    </div>
    <div class="block">
      <dashed-block v-if="dashed" radius="13"></dashed-block>
      <div class="block-body">
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<script>
import dashedBlock from './information-block/dashedBlock.vue'

export default {
  name: 'information-block',
  props: {
    dashed: {
      type: Boolean,
      default: true
    }
  },
  components: {
    dashedBlock
  }
}
</script>

<style scoped>
  .block-head {
    font-family: 'Bebas Neue';
    font-weight: 400;
    font-size: 32px;
    text-align: center;
    margin-top: 40px;
    margin-bottom: 33px;
  }

  .block {
    position: relative;
    max-width: 1000px;
    margin: auto;
  }

  .block-body {
    padding: 30px 20px;
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
  }

  @media (max-width: 1000px) {
    .block-body {
      justify-content: center;
    }
  }
</style>
