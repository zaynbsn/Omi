<template>
  <section class="container">
    <div class="faq d-flex flex-column justify-content-start align-items-center">
      <div class="mb-4">
        <TitleGradient label="F.A.Q"></TitleGradient>
      </div>

      <div v-for="(item, index) in faq" :key="index" class=" d-flex row flex-column justify-content-start align-items-center" style="width: 100%;" >
        <div v-if="!item.isOpen" class="question col-9 d-flex justify-content-start align-items-center mb-4 p-4" @click="switchFaq(item)">
          <img src="@/assets/img/plus.svg" alt="plus" style="width: 24px;">
          <div class="question-text mx-4">{{ item.question }}</div>
        </div>
        
        <div v-if="item.isOpen" class="answer col-9 d-flex flex-column justify-content-center align-items-start mb-4 p-4">
          <div class="question-container d-flex justify-content-start align-items-center mb-3">
            <img src="@/assets/img/minus.svg" alt="moins" style="width: 24px; cursor: pointer;" @click="switchFaq(item)">
            <div class="question-text mx-4">{{ item.question }}</div>
          </div>
          <div class="answer-text">{{ item.answer }}</div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import TitleGradient from '@/components/UI/titleGradient.vue'
import SecondaryButton from '@/components/UI/SecondaryButton.vue'

export default {
  name: 'Faq',
  components: { TitleGradient, SecondaryButton },
  data() {
    return {
      faq: [
        {
          question: 'Comment fonctionne Omi ?',
          answer: `Omi utilise la technologie RFID pour suivre vos objets essentiels. Chaque objet est équipé d'une puce RFID qui communique avec le boîtier intelligent fixé à votre porte. L'étagère multifonctionnelle avec LEDs intégrées vous aide à organiser et à localiser vos objets facilement.`,
          isOpen: false
        },
        {
          question: 'Comment installer Omi chez moi ?',
          answer: `Omi utilise la technologie RFID pour suivre vos objets essentiels. Chaque objet est équipé d'une puce RFID qui communique avec le boîtier intelligent fixé à votre porte. L'étagère multifonctionnelle avec LEDs intégrées vous aide à organiser et à localiser vos objets facilement.`,
          isOpen: false
        },
        {
          question: 'Dois-je recharger Omi ?',
          answer: `Omi utilise la technologie RFID pour suivre vos objets essentiels. Chaque objet est équipé d'une puce RFID qui communique avec le boîtier intelligent fixé à votre porte. L'étagère multifonctionnelle avec LEDs intégrées vous aide à organiser et à localiser vos objets facilement.`,
          isOpen: false
        },
        {
          question: 'Puis-je utiliser Omi avec plus de trois objets ?',
          answer: `Omi utilise la technologie RFID pour suivre vos objets essentiels. Chaque objet est équipé d'une puce RFID qui communique avec le boîtier intelligent fixé à votre porte. L'étagère multifonctionnelle avec LEDs intégrées vous aide à organiser et à localiser vos objets facilement.`,
          isOpen: false
        },
        {
          question: 'Les puces RFIs sont-elles sûres ?',
          answer: `Omi utilise la technologie RFID pour suivre vos objets essentiels. Chaque objet est équipé d'une puce RFID qui communique avec le boîtier intelligent fixé à votre porte. L'étagère multifonctionnelle avec LEDs intégrées vous aide à organiser et à localiser vos objets facilement.`,
          isOpen: false
        },
        {
          question: 'Puis-je obtenir des badges/cartes RFID personnalisées',
          answer: `Omi utilise la technologie RFID pour suivre vos objets essentiels. Chaque objet est équipé d'une puce RFID qui communique avec le boîtier intelligent fixé à votre porte. L'étagère multifonctionnelle avec LEDs intégrées vous aide à organiser et à localiser vos objets facilement.`,
          isOpen: false
        },
        {
          question: "Omi est-il résistant à l'eau ?",
          answer: `Omi utilise la technologie RFID pour suivre vos objets essentiels. Chaque objet est équipé d'une puce RFID qui communique avec le boîtier intelligent fixé à votre porte. L'étagère multifonctionnelle avec LEDs intégrées vous aide à organiser et à localiser vos objets facilement.`,
          isOpen: false
        },
      ]
    }
  },
  methods: {
    switchFaq(item) {
      item.isOpen = !item.isOpen
    }
  }
}
</script>

<style>
.question, .answer{
  background-color: var(--md-blue);
  border-radius: 32px;
  color: white;
}
.question:hover, .answer:hover{
  background-color: black;
  color: #d3d3d3
}
.question{
  cursor: pointer;
}
.question-text{
  font-family: 'Como';
  font-weight: 700;
  font-size: 24px;
}

</style>