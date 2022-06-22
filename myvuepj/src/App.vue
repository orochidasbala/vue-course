<template>
  <div class="sty"><img alt="Vue logo" src="./assets/logo.png" /></div>
  <div align="center">
    <button class="button-37" role="button" @click="showModal = true">
      Open Modal
    </button>
  </div>
  <div v-if="showModal">
    <ModalComponent
      :header="header"
      :contents="content"
      :themes="theme"
      @close="showModal = false"
      :dark="darkMode"
    >
      <!-- <template v-slot:normal v-if="darkMode===false">
        <h1>Welcome To My Page</h1>
        <p>This is my vue project</p>
      </template> -->

      <template v-slot:Dark v-if="darkMode === true">
        <h1>Dark mode turn on</h1>
        <p>This is my new homework</p>
        <div align="center">
          <button class="button-37" role="button" @click="darkMode = !darkMode">
            <span v-if="!darkMode">Dark mode on</span>
            <span v-if="darkMode">Dark mode off</span>
          </button>
        </div>
      </template>

      <template v-slot:Light v-if="darkMode === false">
        <h1>Dark mode turn off</h1>
        <p>This is my new homework</p>
        <div align="center">
          <button class="button-37" role="button" @click="darkMode = !darkMode">
            <span v-if="!darkMode">Dark mode on</span>
            <span v-if="darkMode">Dark mode off</span>
          </button>
        </div>
      </template>

    </ModalComponent>
  </div>
</template>

<script>
import ModalComponent from "./components/ModalComponent.vue";

export default {
  data() {
    return {
      header: "Login success",
      content: "This is my content",
      theme: "delete",
      showModal: false,
      darkMode: false,
    };
  },
  components: {
    ModalComponent,
  },
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.sty {
  text-align: center;
  top: 0;
  position: fixed;
  margin: 70px auto;
  height: 100%;
  width: 100%;
}

/* CSS */
.button-37 {
  background-color: #13aa52;
  border: 1px solid #13aa52;
  border-radius: 10px;
  box-shadow: rgba(0, 0, 0, 0.1) 0 2px 4px 0;
  box-sizing: border-box;
  color: #fff;
  cursor: pointer;
  font-family: "Akzidenz Grotesk BQ Medium", -apple-system, BlinkMacSystemFont,
    sans-serif;
  font-size: 16px;
  font-weight: 400;
  outline: none;
  outline: 0;
  padding: 10px 25px;
  margin: 5px;
  text-align: center;
  width: 200px;
  transform: translateY(0);
  transition: transform 150ms, box-shadow 150ms;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
}

/*.button-37:hover {
  box-shadow: rgba(0, 0, 0, .15) 0 3px 9px 0;
  transform: translateY(-2px);
}*/

/*@media (min-width: 768px) {
  .button-37 {
    padding: 10px 30px;
  }
}*/
</style>
