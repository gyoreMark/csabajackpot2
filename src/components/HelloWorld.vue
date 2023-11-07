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
              <p class="card-text">
                {{ this.random1 }}
              </p>
              <i class="fa-solid fa-x" id="icon1"></i>
            </div>
          </div>
        </div>
        <div class="col-md-4" id="ezt">
          <div class="card">
            <div class="card-body">
              <p class="card-text">
                {{ this.random2 }}
              </p>
              <i class="fa-solid fa-x" id="icon2"></i>
            </div>
          </div>
        </div>
        <div class="col-md-4">
          <div class="card">
            <div class="card-body">
              <p class="card-text">
                {{ this.random3 }}
              </p>
              <i class="fa-solid fa-x" id="icon3"></i>
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
        <div class="d-grid gap-2 nyert" id="nyeremeny">{{ nyeremeny }}</div>
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
        { name: "Citrom", icon: "fa-solid fa-lemon" },
        { name: "ALma", icon: "fa-solid fa-apple-whole" },
        { name: "Levél", icon: "fa-solid fa-leaf" },
        { name: "Chili", icon: "fa-solid fa-pepper-hot" },
        { name: "Répa", icon: "fa-solid fa-carrot" },
      ],

      ideaGyumolcsot: 0, //???

      random1: undefined,
      random2: undefined,
      random3: undefined,

      nyeremeny1: "Nyertél!",
      nyeremeny2: "Nem nyertél!",
      nyeremeny3: "Mega Jackpot!",
    };
  },

  methods: {
    gyumolcsMegjelenik() {
      // const randomIndex = Math.floor(Math.random() * this.gyumolcsok.length);
      // this.ideaGyumolcsot = this.gyumolcsok[randomIndex];

      // random szám generálása ez elsz a randomIndex
      const randomIndex = Math.floor(Math.random() * this.gyumolcsok.length);
      //a random1 a gyumolcsok tömb randomindexedik elemének neve lesz
      this.random1 = this.gyumolcsok[randomIndex].name;
      //console.log(this.random1);

      //a myIcon az icon1 azonosítójú html elem lesz tehát az ikon
      let myIcon = document.getElementById("icon1");

      //az ikon class tulajdonságát változtatjuk meg a gyumolcsok tömb randomIndexedik elemének az icon-jára
      myIcon.setAttribute("class", this.gyumolcsok[randomIndex].icon);

      const randomIndex2 = Math.floor(Math.random() * this.gyumolcsok.length);
      this.random2 = this.gyumolcsok[randomIndex2].name;

      let myIcon2 = document.getElementById("icon2");

      myIcon2.setAttribute("class", this.gyumolcsok[randomIndex2].icon);

      const randomIndex3 = Math.floor(Math.random() * this.gyumolcsok.length);
      this.random3 = this.gyumolcsok[randomIndex3].name;
      let myIcon3 = document.getElementById("icon3");

      myIcon3.setAttribute("class", this.gyumolcsok[randomIndex3].icon);

      if (this.random1 == this.random2) {
        console.log("Nyertél!");
        this.nyeremeny = this.nyeremeny1;
        this.nyertelFelirat = document.getElementById("nyeremeny").style.color =
          "greenyellow";
      } else if (this.random1 == this.random3) {
        console.log("Nyertél!");
        this.nyeremeny = this.nyeremeny1;
        this.nyertelFelirat = document.getElementById("nyeremeny").style.color =
          "greenyellow";
      } else if (this.random2 == this.random3) {
        console.log("Nyertél!");
        this.nyeremeny = this.nyeremeny1;
      } else if (
        this.random1 === this.random2 &&
        this.random2 === this.random3
      ) {
        console.log("MEGA JACKPOT!");
        this.nyeremeny = this.nyeremeny3;
        this.nyertelFelirat = document.getElementById("nyeremeny").style.color =
          "greenyellow";
      } else {
        console.log("Nem nyertél!");
        this.nyeremeny = this.nyeremeny2;
        //this.nemnyertFelirat = document.setAttribute("class", this.nemnyert); ????????????????
        this.nemnyertFelirat = document.getElementById(
          "nyeremeny"
        ).style.color = "red";
      }

      //document.getElementById("ezt").style.backgroundColor = "red";
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
  background-color: #233452;
  width: 100%;
  height: 100%;
  left: 0;
  top: 0;
}

.title {
  margin-bottom: 25px;
  color: white;
}

#btnStyle {
  margin-top: 25px;
}

.nyert {
  color: greenyellow;
  font-family: fantasy;
  font-size: 50px;
  font-variant: small-caps;
}

.nemnyert {
  color: red;
  font-family: fantasy;
  font-size: 50px;
  font-variant: small-caps;
}
</style>