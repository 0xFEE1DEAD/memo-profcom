<template>
    <div class="micro-contact">
        <div class="micro-contact-background" :style="backStyle">
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
  },
  props: {
    backRotate: {
      type: Number,
      default: 0
    }
  },
  computed: {
      backStyle () {
        return { transform: 'rotate(' + this.backRotate + 'deg)'}
     }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .micro-contact {
      position: relative; 
      width: 400px;
      margin: auto;
  }
  .micro-contact-background {
      width: 400px; 
      height: 400px; 
      position: absolute; 
      z-index: -9999999;
  }
  .micro-contact-body {
    width: 300px; 
    min-height: 300px;
    margin: auto; 
    margin-top: 50px;
    border-radius: 60px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background-color: white;
    box-shadow: 0 0 20px rgb(0,0,0,.15);
    transition-property: box-shadow;
    transition-duration: 200ms;
    background-image: url("../assets/images/pattern.svg");
  }

  .micro-contact-body:hover {
    box-shadow: 0 0 40px rgba(2, 37, 63, 0.3);
  }

  .micro-contact-body-title {
    font-family: 'Bebas Neue';
    font-weight: 400;
    font-size: 28px;
  }

  @media (max-width: 880px) {
    .micro-contact-body-title {
      font-size: 25px;
    }
    .micro-contact {
        width: 320px;
    }
    .micro-contact-background {
      width: 320px; 
      height: 320px; 
    }
    .micro-contact-body {
      width: 260px;
      min-height: 260px;
      margin-top: 30px;
    }
  }
  @media (max-width: 350px) {
    .micro-contact-body-title {
      font-size: 22px;
    }
    .micro-contact {
        width: 300px;
    }
    .micro-contact-background {
      width: 300px; 
      height: 300px; 
    }
    .micro-contact-body {
      width: 260px;
      min-height: 260px;
      margin-top: 30px;
    }
  }
</style>
