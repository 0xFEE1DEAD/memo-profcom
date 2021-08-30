<template>
    <div class="micro-contact">
        <div class="micro-contact-background">
            <abstract-figure></abstract-figure>
        </div>
        <div class="micro-contact-body">
            <div class="micro-contact-body-title">
                <slot name="title"></slot>
            </div>
            <slot></slot>
        </div>
    </div>
</template>

<script>
import abstractFigure from './abstractFigure.vue'

export default {
  name: 'micro-contact-block',
  components: {
      abstractFigure
  }
  /*props: {
    msg: String
  }*/
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .micro-contact {
      position: relative; 
      width: 400px;
  }
  .micro-contact-background {
      width: 400px; 
      height: 400px; 
      position: absolute; 
      z-index: -9999999;
  }
  .micro-contact-body {
    width: 300px; 
    height: 300px;
    margin: auto; 
    margin-top: 50px;
    border-radius: 60px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background-color: white;
    background-image: url("../assets/images/pattern.svg");
  }

  .micro-contact-body-title {
    font-family: 'Bebas Neue';
    font-weight: 400;
    font-size: 28px;
  }
</style>
