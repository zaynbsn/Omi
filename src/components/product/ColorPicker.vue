<template>
  <div class="colorpicker d-flex flex-column justify-content-center align items-center" style="width: fit-content">
    <img class="picker" src="@/assets/img/personalize/defaultPicker.svg" alt="" @click="emitColorChange(0)">
    <img class="picker" src="@/assets/img/personalize/gradientPicker2.svg" alt="" @click="emitColorChange(1)">
    <img class="picker" src="@/assets/img/personalize/gradientPicker1.svg" alt="" @click="emitColorChange(2)">
    <img class="picker" src="@/assets/img/personalize/orangePicker.svg" alt="" @click="emitColorChange(3)">
    <img class="picker" src="@/assets/img/personalize/purplePicker.svg" alt="" @click="emitColorChange(4)">
    <img class="picker" src="@/assets/img/personalize/bluePicker.svg" alt="" @click="emitColorChange(5)">
  </div>
</template>

<script>

export default {
  name: 'ColorPicker',
  data() {
    return {
      toto: 'tutu'
    }
  },
  methods: {
    emitColorChange(id) {
      this.$emit('changeColor', id);
    },
  }
}
</script>

<style scoped>
.colorpicker{
  margin-left: 25%;
  z-index: 10;
}
.picker{
  width: 48px;
  height: auto;
  margin-bottom: 16px;
}
</style>