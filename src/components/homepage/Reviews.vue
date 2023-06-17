<template>
  <section class="container">
      <div class="reviews-container row d-flex flex-column align-items-center justify-content-center" style="margin: 32px 0;">
        <div class=" col-9 mb-5">
          <TitleGradient label="La satisfaction de nos clients avant tout"></TitleGradient>
        </div>

        <div class="reviews row d-flex align-items-center justify-content-center p-4">
          <div v-for="(review, index) in reviews" :key="index" class="review-card col d-flex flex-column justify-content-center align-items-start p-4 m-2">
            <div class="author col d-flex justify-content-center align-items-center mb-3">
              <img src="@/assets/img/profilePictureDefault.svg" alt="profile picture" style="margin-right: 1rem; width: 32px;">
              <div class="name">{{ review.author }}</div>
            </div>

            <div class="grade d-flex justify-content-start align-items-center  mb-3">
              <img src="@/assets/img/orangeStar.svg" alt="orange star" class="star">
              <img src="@/assets/img/orangeStar.svg" alt="orange star" class="star">
              <img src="@/assets/img/orangeStar.svg" alt="orange star" class="star">
              <img src="@/assets/img/orangeStar.svg" alt="orange star" class="star">
              <img src="@/assets/img/greyStar.svg" alt="grey star" class="star">
            </div>

            <div class="review-text">{{ review.content }}</div>
          </div>
        </div>
      </div>
    </section>
</template>

<script>
import { ref } from 'vue'
import TitleGradient from '@/components/UI/TitleGradient.vue'

export default {
  name: 'Reviews',
  components: { TitleGradient },
  setup() {
    const reviews = ref([
      {
        author: 'Julie L.',
        grade: 4,
        content: `"J'étais constamment en retard parce que je ne trouvais jamais mes clés. Omi a changé ma vie ! Je recommande fortement."`
      },
      {
        author: 'Martin D.',
        grade: 4,
        content: `"Très pratique et esthétiquement plaisant. J'aurais aimé un choix plus large de couleurs, mais le produit fonctionne très bien."` 
      },
      {
        author: 'Isabelle P.',
        grade: 4,
        content: `"Un must-have pour tout le monde ! C'est fou comme on s'habitue vite à ce petit bijou de technologie. Adieu le stress du matin !"`
      },
    ])

    return { reviews }
  }
}
</script>

<style scoped>
.reviews{
  background-color: var(--lavander);
  border-radius: 32px;
  height: 300px;
  width: 100%;
}
.review-card{
  border: 1px solid white;
  background-color: var(--md-blue);
  border-radius: 16px;
  color: white;
}
.name{
  font-family: 'Como';
  font-weight: 400;
  font-size: 25,89px;
}
.star{
  width: auto;
  height: 24px;
  margin-right: 0.5rem;
}
.star img{
  width: 100%;
  height: auto;  
}
.review-text{
  font-family: 'Montserrat', sans-serif;
  font-weight: 400;
  font-size: 16px;
}
</style>