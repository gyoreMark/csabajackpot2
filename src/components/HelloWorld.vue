<template>
  <div class="background">
    <div class="container">
      <h1 class="title">
        <i class="fa-solid fa-coins" style="color: #ffffff"></i> Coin Machine
        <i class="fa-solid fa-coins" style="color: #ffffff"></i>
      </h1>
      <div class="row">
        <div class="col-md-4">
          <div class="card">
            <div class="card-body">
              <p class="card-text" v-if="ideaGyumolcsot">
                {{ ideaGyumolcsot.icon }}
              </p>
            </div>
          </div>
        </div>
        <div class="col-md-4">
          <div class="card">
            <div class="card-body">
              <p class="card-text" v-if="ideaGyumolcsot">
                {{ ideaGyumolcsot.icon }}
              </p>
            </div>
          </div>
        </div>
        <div class="col-md-4">
          <div class="card">
            <div class="card-body">
              <p class="card-text" v-if="ideaGyumolcsot">
                {{ ideaGyumolcsot.icon }}
              </p>
            </div>
          </div>
        </div>
        <div class="d-grid gap-2" id="btnStyle">
          <button
            class="btn btn-outline-light"
            type="button"
            @click="gyumolcsMegjelenik"
          >
            Játék
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },

  data() {
    return {
      gyumolcsok: [
        { name: "Citrom", icon: '<i class="fa-solid fa-lemon"></i>' },
        { name: "ALma", icon: '<i class="fa-solid fa-apple-whole"></i>' },
        { name: "Levél", icon: '<i class="fa-solid fa-leaf"></i>' },
        { name: "Chili", icon: '<i class="fa-solid fa-pepper-hot">' },
        { name: "Répa", icon: '<i class="fa-solid fa-carrot">' },
      ],

      ideaGyumolcsot: 0, //???
    };
  },

  methods: {
    gyumolcsMegjelenik() {
      // const randomIndex = Math.floor(Math.random() * this.gyumolcsok.length);
      // this.ideaGyumolcsot = this.gyumolcsok[randomIndex];
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.background {
  position: absolute;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-color: red;
  width: 100%;
  height: 100%;
  left: 0;
  top: 0;
}

.title {
  margin-bottom: 25px;
}

#btnStyle {
  margin-top: 25px;
}
</style>
