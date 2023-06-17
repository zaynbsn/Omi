<template>
  <router-link class="main-button" :class="black ? 'black' : ''" :to="to">{{ label }}</router-link>
</template>

<script>

export default {
  name: 'MainButton',
  props: {
    label: {
      type: String,
      required: true
    },
    to: {
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
.main-button{
  background: -webkit-linear-gradient(0deg, var(--purple) 20%, var(--blue) 99%);
  border-radius: 8px;
  padding: 10px 24px;
  text-decoration: none;
  color: white;
  font-family: 'Montserrat', sans-serif;
  font-weight: 500;
  font-size: 18px;
  letter-spacing: 1px;
  text-align: center;
  width: fit-content;
  cursor: pointer;
}

.black{
  background: var(--md-blue);

}
</style>