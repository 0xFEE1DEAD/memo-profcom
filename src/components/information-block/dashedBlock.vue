<template>
    <svg :style="'z-index:-999999;border-radius:' + radius + 'px;' + 'position: absolute;'" 
            width='100%' height='100%' xmlns='http://www.w3.org/2000/svg'>
        <rect 
            width='100%' 
            height='100%' 
            fill='none'
            :rx='radius'
            :ry='radius'
            :stroke='color' 
            :stroke-width='width' 
            :stroke-dasharray='dasharray' 
            stroke-dashoffset='0' 
            stroke-linecap='square'/>
    </svg>
</template>

<script>
export default {
  name: 'dashed-block',
  props: {
    dasharray: {
      type: String,
      default: '4,16'
    },
    width: {
        type: Number,
        default: 6
    },
    color: {
        type: String,
        default: '#222'
    },
    radius: {
        type: String,
        default: '0'
    }
  }
}
</script>
