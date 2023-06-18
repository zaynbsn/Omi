<template>
  <router-link class="main-button" :class="black ? 'black' : ''" :to="to">
    <span>{{ label }}</span>
    <img src="../../assets/img/hover-icon.svg" alt="icon" class="hover-icon" />
  </router-link>
  
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
.main-button span{
  text-align: center;
}
.hover-icon{
  width: 0;
  height: auto;
  margin-left: 0px;
  margin-right: 0px;
  transition: 0.2s;
}
.main-button:hover .hover-icon{
  width: 24px;
  margin-left: 8px;
  margin-right: -8px;
}
</style>