<template>
  <div :class="[{flexStart: step === 1}, 'wrapper']">
    <transition name="slide">
          <img 
          src="./assets/logo.svg" 
          alt="logo" 
          class="logo" 
          v-if="step === 1"
          />
    </transition>
    <transition name="fade">
      <HeroImage v-if="step === 0"/>
    </transition>
    <Claim v-if="step === 0"/>
    <SearchInput 
    v-model="searchValue"
    @input="inputHandle"
    :dark="step === 1"
    />
    <Loader v-if="step === 1 && loading"/>
   <div class="results" 
   v-if="results && !loading & step === 1">
     <Item 
     v-for="item in results" 
     :item="item" 
     :key="item.data[0].nasa_id"
     @click.native="handleModalOpen(item)"
     
     />
   </div>
   <Modal 
    v-if="modalOpen"
    @closeModal="modalOpen = false"
    :item="modalItem"
    />
  </div>
</template>

<script>
import HeroImage from "@/components/HeroImage.vue";
import Loader from "@/components/Loader.vue";
import Item from "@/components/Item.vue";
import Modal from "@/components/Modal.vue";
import Claim from "@/components/Claim.vue";
import SearchInput from "@/components/SearchInput.vue";
import axios from "axios";
import debounce from "lodash.debounce";
export default {
  name: "App",
  components: {
    Claim,
    SearchInput,
    HeroImage,
    Item,
    Modal,
    Loader
  },
  data() {
    return {
      modalItem: null,
      modalOpen: false,
      loading: false,
      step: 0,
      //bind to v-model
      searchValue: "",
      results: []
    };
  },
  methods: {
    handleModalOpen(item) {
      this.modalOpen = true;
      this.modalItem = item;
    },
    inputHandle: debounce(function() {
      this.loading = true;
      axios
        .get(
          `https://images-api.nasa.gov/search?q=${
            this.searchValue
          }&media_type=image`
        )
        .then(res => {
          this.results = res.data.collection.items;
          this.loading = false;
          this.step = 1;
        })
        .catch(err => console.log(err));
    }, 500)
  }
};
</script>


<style lang="scss">
@import url("https://fonts.googleapis.com/css?family=Montserrat:300,400,600,800");
* {
  box-sizing: border-box;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
body {
  font-family: "Montserrat", sans-serif;
  padding: 0;
  margin: 0;
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
.slide-enter-active,
.slide-leave-active {
  transition: margin-top 0.3s ease;
}
.slide-enter, .slide-leave-to /* .fade-leave-active below version 2.1.8 */ {
  margin-top: -50px;
}
.wrapper {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  margin: 0;
  padding: 30px;
  min-height: 100vh;
  justify-content: center;
  &.flexStart {
    justify-content: flex-start;
  }
}
.logo {
  margin-bottom: 15px;
}
.results {
  margin-top: 50px;
  display: grid;
  grid-template-columns: 1fr;
  grid-gap: 20px;

  @media (min-width: 768px) {
    grid-template-columns: repeat(2, 1fr);
  }
  @media (min-width: 1024px) {
    grid-template-columns: repeat(3, 1fr);
  }
}
</style>

