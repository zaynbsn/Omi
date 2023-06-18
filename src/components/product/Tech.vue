<template>
  <section class="container">
    <div class="tech d-flex flex-column justify-content-center align-items-center">
      <TitleGradient label="Fiche technique" style="font-size: 42px!important; margin-bottom: 32px"></TitleGradient>

      <div class="details row justify-content-center">
        <div v-for="(item, index) in tech" :key="index" class="mirror col-sm-6 d-flex flex-column justify-content-center align-items-center">
          <TitleGradient :label="item.label" style="font-size: 32px!important; margin-bottom: 16px"></TitleGradient>

          <div class="mirror-infos">
            <div class="infos-infos d-flex flex-column justify-content-center align-items-start">
              <div v-for="(component, index) in item.components" :key="index">
                <span>{{ component }}</span>
                <div class="line my-2"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { ref } from 'vue'
import TitleGradient from '@/components//UI/TitleGradient.vue';
export default {
  name: "Tech",
  components: { TitleGradient },
  setup() {
    const tech = ref([
      {
        label: 'Miroir',
        components: ['ESP32', 'Bandeau led', 'Capteur ultrason', 'Lecteurs RFID'],
      },
      {
        label: 'Boîtier',
        components: ['ESP32', 'Bandeau led', 'Capteur ultrason', 'Acceleromètre'],
      }
    ])

    return {tech}
  }
}
</script>

<style scoped>
.details{
  background-color: var(--lavander);
  border-radius: 32px;
  padding: 32px;
}
.mirror-infos, .case-infos{
  background-color: var(--md-blue);
  border-radius: 16px;
  padding: 32px 152px 32px 48px;
  color: white;
}
.line{
  background-color: #443385;
  width: 175%;
  height: 1px;
}
span{
  font-family: 'Montserrat', sans-serif;
  font-weight: 400;
  font-size: 14px;
}
</style>