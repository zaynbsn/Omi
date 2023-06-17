<template>
  <div class="title-gradient" :class="left ? 'left' : ''">{{ label }}</div>
</template>

<script>

export default {
  name: 'TitleGradient',
  props: {
    label: {
      type: String,
      required: true
    },
    left: {
      type: Boolean,
      required: false,
      default: false
    }
  }
}
</script>

<style scoped>
.title-gradient{
  font-family: 'Como';
  font-weight: 700;
  font-size: 67.77px;
  background: -webkit-linear-gradient(0deg, var(--purple) 20%, var(--blue) 99%);
  text-align: center;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.left{
  text-align: left;
}

@media screen and (max-width: 768px){
  .title-gradient{
    font-size: 36px;
  }
}
</style>