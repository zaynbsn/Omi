<template>
  <a class="secondary-button" :class="black ? 'black' : ''">{{ label }}</a>
</template>

<script>

export default {
  name: 'SecondaryButton',
  props: {
    label: {
      type: String,
      required: true
    },
    left: {
      type: Boolean,
      required: false,
      default: false
    },
    black: {
      type: Boolean,
      required: false,
      default: false
    }
  }
}
</script>

<style scoped>
.secondary-button{
  background: var(--purple);
  border-radius: 8px;
  padding: 10px 24px;
  text-decoration: none;
  color: white;
  font-family: 'Montserrat', sans-serif;
  font-weight: 500;
  font-size: 25.89px;
  letter-spacing: 1px;
  text-align: center;
}
.black{
  background: var(--md-blue);

}
</style>