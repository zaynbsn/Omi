<template>
  <router-link class="secondary-button" :class="black ? 'black' : ''"  :to="to">
    {{ label }}
    <img src="../../assets/img/hover-icon.svg" alt="icon" class="hover-icon" />
  </router-link>
</template>

<script>

export default {
  name: 'SecondaryButton',
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
.secondary-button{
  background: var(--purple);
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
.secondary-button span{
  text-align: center;
}
.black{
  background: var(--md-blue);
}
.hover-icon{
  width: 0;
  height: auto;
  margin-left: 0px;
  margin-right: 0px;
  transition: 0.2s;
}
.secondary-button:hover .hover-icon{
  width: 24px;
  margin-left: 8px;
  margin-right: -8px;
}
</style>