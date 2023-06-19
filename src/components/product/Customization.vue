<template>
  <section class="homehead bg-gradient" :style="!isMobile ? 'margin-bottom: 128px;' : 'margin-bottom: 72px 0;'">
    <div v-if="currentSection == getOmiEnum" class="container" >
      <div class="title-container d-flex align-items-center justify-content-start">
        <div class="content-container d-flex flex-column align-items-center justify-content-center" style="width: 50%; margin-top: -10rem; ">
          <div class="subcontainer">
            <h1 class="title">Omi</h1>
            <p class="subtitle">Le vide-poche connecté</p>
            <div class="price">
              <div class="price-text">199 €</div>
            </div>
          </div>
        </div>
        <div class="omi-gif d-flex align-items-center justify-content-center" style="overflow-x: hidden; margin-left: 16px" >
          <img src="@/assets/gifs/omi.gif"/>
        </div>
        
      </div>
      <div class="next-button d-flex justify-content-center align-items-center" style="z-index: 2; margin-top: -2rem" @click="currentSection = getWalletEnum">
        <SecondaryButton label="Choisir mes badges" black to=""></SecondaryButton>
      </div>
    </div>

    <div v-if="currentSection == getWalletEnum" class="container">
      <div class="title-container d-flex align-items-center justify-content-start">
        <div class="content-container d-flex flex-column align-items-center justify-content-center" style="width: 50%; margin-top: -10rem; ">
          <div class="subcontainer">
            <h1 class="title">Badge Portefeuille</h1>
          </div>
        </div>
        <div class="omi-gif wallet-card d-flex align-items-center justify-content-center" style="overflow-x: hidden; margin-left: 16px" >
          <img v-if="walletColor == getDefaultEnum" src="@/assets/img/personalize/card.png"/>
          <img v-if="walletColor == getGradient2Enum" src="@/assets/img/personalize/gradientCard2.png"/>
          <img v-if="walletColor == getGradient1Enum" src="@/assets/img/personalize/gradientCard1.png"/>
          <img v-if="walletColor == getOrangeEnum" src="@/assets/img/personalize/orangeCard.png"/>
          <img v-if="walletColor == getPurpleEnum" src="@/assets/img/personalize/purpleCard.png"/>
          <img v-if="walletColor == getBlueEnum" src="@/assets/img/personalize/blueCard.png"/>
        </div>
        <colorPicker @changeColor="handleColorChangeWallet"></colorPicker>
        
      </div>
      <div class="d-flex justify-content-center align-items-center">
        <div class="next-button d-flex justify-content-center align-items-center mx-3" style="z-index: 2; margin-top: -2rem" @click="currentSection = getOmiEnum">
          <SecondaryButton label="Retour" black to=""></SecondaryButton>
        </div>
        <div class="next-button d-flex justify-content-center align-items-center" style="z-index: 2; margin-top: -2rem"  @click="currentSection = getKeyEnum">
          <SecondaryButton label="Badge suivant" black to=""></SecondaryButton>
        </div>
      </div>
    </div>
  
    <div v-if="currentSection == getKeyEnum" class="container">
      <div class="title-container d-flex align-items-center justify-content-start">
        <div class="content-container d-flex flex-column align-items-center justify-content-center" style="width: 50%; margin-top: -10rem; ">
          <div class="subcontainer">
            <h1 class="title">Badge clefs de maison</h1>
          </div>
        </div>
        <div class="omi-gif key-badge d-flex align-items-center justify-content-center" style="overflow-x: hidden; margin-left: 16px" >
          <img v-if="keyColor == getDefaultEnum" src="@/assets/img/personalize/keyBadge.png"/>
          <img v-if="keyColor == getGradient2Enum" src="@/assets/img/personalize/gradientKeyBadge2.png"/>
          <img v-if="keyColor == getGradient1Enum" src="@/assets/img/personalize/gradientKeyBadge1.png"/>
          <img v-if="keyColor == getOrangeEnum" src="@/assets/img/personalize/orangeKeyBadge.png"/>
          <img v-if="keyColor == getPurpleEnum" src="@/assets/img/personalize/purpleKeyBadge.png"/>
          <img v-if="keyColor == getBlueEnum" src="@/assets/img/personalize/blueKeyBadge.png"/>
        </div>
        <colorPicker @changeColor="handleColorChangeKey"></colorPicker>
        
      </div>
      <div class="d-flex justify-content-center align-items-center">
        <div class="next-button d-flex justify-content-center align-items-center mx-3" style="z-index: 2; margin-top: -2rem" @click="currentSection = getWalletEnum">
          <SecondaryButton label="Retour" black to=""></SecondaryButton>
        </div>
        <div class="next-button d-flex justify-content-center align-items-center" style="z-index: 2; margin-top: -2rem" @click="currentSection = getCarEnum">
          <SecondaryButton label="Badge suivant" black to="" ></SecondaryButton>
        </div>
      </div>
    </div>
  
    <div v-if="currentSection == getCarEnum" class="container">
      <div class="title-container d-flex align-items-center justify-content-start">
        <div class="content-container d-flex flex-column align-items-center justify-content-center" style="width: 50%; margin-top: -10rem; ">
          <div class="subcontainer">
            <h1 class="title">Badge clefs de voiture</h1>
          </div>
        </div>
        <div class="omi-gif key-badge d-flex align-items-center justify-content-center" style="overflow-x: hidden; margin-left: 16px" >
          <img v-if="carColor == getDefaultEnum" src="@/assets/img/personalize/keyBadge.png"/>
          <img v-if="carColor == getGradient2Enum" src="@/assets/img/personalize/gradientKeyBadge2.png"/>
          <img v-if="carColor == getGradient1Enum" src="@/assets/img/personalize/gradientKeyBadge1.png"/>
          <img v-if="carColor == getOrangeEnum" src="@/assets/img/personalize/orangeKeyBadge.png"/>
          <img v-if="carColor == getPurpleEnum" src="@/assets/img/personalize/purpleKeyBadge.png"/>
          <img v-if="carColor == getBlueEnum" src="@/assets/img/personalize/blueKeyBadge.png"/>
        </div>
        <colorPicker @changeColor="handleColorChangeCar"></colorPicker>
        
      </div>
      <div class="d-flex justify-content-center align-items-center">
        <div class="next-button d-flex justify-content-center align-items-center mx-3" style="z-index: 2; margin-top: -2rem" @click="currentSection = getKeyEnum">
          <SecondaryButton label="Retour" black to=""></SecondaryButton>
        </div>
        <div class="next-button d-flex justify-content-center align-items-center" style="z-index: 2; margin-top: -2rem">
          <SecondaryButton label="Passez à l'achat" black to=""></SecondaryButton>
        </div>
      </div>
    </div>

  </section>

</template>

<script>
import SecondaryButton from '@/components/UI/SecondaryButton.vue';
import { productEnum, colorPickerEnum } from '@/enums/modules/ProductEnum'
import colorPicker from '@/components/product/colorPicker.vue'
import windowWidthMixin from '@/mixins/windowWidthMixin';

export default {
    name: "Customization",
    components: { SecondaryButton, colorPicker },
    mixins: [ windowWidthMixin ],
    data() {
      return {
        currentSection: productEnum.OMI,
        walletColor: colorPickerEnum.DEFAULT,
        keyColor: colorPickerEnum.DEFAULT,
        carColor: colorPickerEnum.DEFAULT,
        colors: {
          0: 'default'
        } 
      }
    },
    computed: {
      getOmiEnum() {
        return productEnum.OMI
      },
      getWalletEnum() {
        return productEnum.WALLETCARD
      },
      getKeyEnum() {
        return productEnum.KEYBADGE
      },
      getCarEnum() {
        return productEnum.CARKEYBADGE
      },
      getDefaultEnum() {
        return colorPickerEnum.DEFAULT
      },
      getGradient2Enum() {
        return colorPickerEnum.GRADIENT2
      },
      getGradient1Enum() {
        return colorPickerEnum.GRADIENT1
      },
      getOrangeEnum() {
        return colorPickerEnum.ORANGE
      },
      getPurpleEnum() {
        return colorPickerEnum.PURPLE
      },
      getBlueEnum() {
        return colorPickerEnum.BLUE
      },
    },
    methods: {
      handleColorChangeWallet(id) {
        switch (id) {
          case 0:
            this.walletColor = colorPickerEnum.DEFAULT
            break
          case 1:
            this.walletColor = colorPickerEnum.GRADIENT2
            break
          case 2:
            this.walletColor = colorPickerEnum.GRADIENT1
            break
          case 3:
            this.walletColor = colorPickerEnum.ORANGE
            break
          case 4:
            this.walletColor = colorPickerEnum.PURPLE
            break
          case 5:
            this.walletColor = colorPickerEnum.BLUE
            break
          default:
            break
        }
      },
      handleColorChangeKey(id) {
        switch (id) {
          case 0:
            this.keyColor = colorPickerEnum.DEFAULT
            break
          case 1:
            this.keyColor = colorPickerEnum.GRADIENT2
            break
          case 2:
            this.keyColor = colorPickerEnum.GRADIENT1
            break
          case 3:
            this.keyColor = colorPickerEnum.ORANGE
            break
          case 4:
            this.keyColor = colorPickerEnum.PURPLE
            break
          case 5:
            this.keyColor = colorPickerEnum.BLUE
            break
          default:
            break
        }
      },
      handleColorChangeCar(id) {
        switch (id) {
          case 0:
            this.carColor = colorPickerEnum.DEFAULT
            break
          case 1:
            this.carColor = colorPickerEnum.GRADIENT2
            break
          case 2:
            this.carColor = colorPickerEnum.GRADIENT1
            break
          case 3:
            this.carColor = colorPickerEnum.ORANGE
            break
          case 4:
            this.carColor = colorPickerEnum.PURPLE
            break
          case 5:
            this.carColor = colorPickerEnum.BLUE
            break
          default:
            break
        }
      }
    }
}
</script>

<style scoped>
.homehead{
  height: 90vh;
}
.bg-gradient{
  background: linear-gradient(90deg, var(--purple) 0%, var(--blue) 99%)!important;
}
.title-container{
  height: 75vh;
}
.subcontainer{
  width: 30%;
}
.title{
  font-family: 'Como';
  font-weight: 700;
  font-size: 40px;
  color: white;
  text-align: left;
  z-index: 2;
  width: fit-content;
}
.subtitle{
  font-family: 'Como';
  font-weight: 500;
  font-size: 14px;
  color: white;
  text-align: left;
  z-index: 2;
  width: fit-content;
}
.price{
  background-color: var(--lavander);
  border-radius: 16px;
  padding: 8px 16px;
  align-self: flex-start;
  z-index: 2;
  width: fit-content;
}
.price-text{
  font-family: 'Como';
  font-weight: 500;
  font-size: 24px;
}
.omi-gif{
  position: absolute;
  left: 0;
  width: 100%;
  z-index: 1;
}
.wallet-card, .key-badge{
  width: 100%;
  margin-top: 64px;
}
.key-badge img{
  width: 60%;
}
.wallet-card img{
  width: 45%;
}
.round-section{
  width: 100%;
  background-color: white;
  border-radius: 96px 96px 0 0;
  height: 125px;
  margin-top: -24px;
}

@media screen and (max-width: 768px) {
  .title{
    font-size: 64px;
  }
  .round-section{
    height: 85px;
    margin-top: 15px;
  }
}
</style>