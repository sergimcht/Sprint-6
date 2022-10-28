<template>
  <div v-if="displayWlcm" id="wlcm">
    <h2>SAMPLE TUTORIAL</h2>
    <p>
      Lorem ipsum dolor, sit amet consectetur adipisicing elit. Quam blanditiis officiis quasi architecto molestias, obcaecati id consectetur quisquam doloribus quo aspernatur fuga, fugiat sit exercitationem, facilis excepturi voluptatem rem hic dicta incidunt explicabo! Sit mollitia unde cum quis iure, ipsa dignissimos explicabo fugit aperiam ullam tempora ipsum omnis dicta cumque dolores tenetur? Deleniti ducimus commodi praesentium incidunt dolorem, quam dolorum maiores blanditiis quia laborum laboriosam inventore esse magni sed recusandae?  
    </p>
    <button @click="alternatePlotMenu">COMENÇAR</button>
  </div>
  <div v-if="displayPlotMenu">
    <Botons @alternatePhrase="alternatePhrase" @alternatePlotMenu="alternatePlotMenu"/>
    <Scene :plot="plot" :currentPhrase="currentPhrase" />
    <img :src="require(`../assets/${currentImg}.jpg`)" alt="" />
  </div>
</template>

<script>
import Botons from "./Botons.vue";
import Scene from "./Scene.vue";

export default {
  name: "Home",
  components: { Botons, Scene },
  props: [],
  data() {
    return {
      plot : [
        {
            txt: "El nostre heroi estava surant per l'espai sideral quan a la llunyania va albirar una nau espacial.",
            img: "1.jpg",
            index: 1
        },
        {
            txt: "Sentia curiositat per l'interior de la nau i es va posar a inspeccionar-la. Va arribar a una sala amb dues portes.",
            img: "2.jpg",
            index: 2
        },
        {
            txt: "L'heroi va decidir travessar la porta que el portava a casa.",
            img: "3.jpg",
            index: 3
        },
        {
            txt: "Mentrestant, altres herois no van tenir tanta sort en la seva elecció...",
            img: "4.jpg",
            index: 4
        }
      ],
      displayWlcm: true,
      displayPlotMenu: false,
      currentPhrase: 0,
      currentImg: 1,
    };
  },
  methods: {
    alternatePhrase(id) {
      if (id === 1) {
        this.currentPhrase--;
        this.currentImg--;
      } else if (id === 2) {
        this.currentPhrase++;
        this.currentImg++;
      }
      //per reiniciar el bucle
      if (this.currentPhrase < 0) this.currentPhrase = 3;
      if (this.currentPhrase > 3) this.currentPhrase = 0;
      if (this.currentImg < 1) this.currentImg = 4;
      if (this.currentImg > 4) this.currentImg = 1;
    },
    alternatePlotMenu() {
      this.displayPlotMenu = !this.displayPlotMenu;
      this.displayWlcm = !this.displayWlcm;
    },
  },
};
</script>

<style>
img {
  position: fixed;
  top: 0;
  z-index: -1;
  width: 100vw;
  height: 100vh;
}
#wlcm {
  background: linear-gradient(rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.6)), url("../assets/home_bg.jpg") center/cover;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  text-align: center;
  justify-content: center;
  align-items: center;
  
}
#wlcm h2 {
  font-size: 6rem;
  color: rgb(220, 200, 20);
  font-weight: 700;
  text-shadow: -1px -1px 0 rgb(255, 0, 0), 1px -1px 0 rgb(0, 85, 255), -1px 1px 0 rgb(255, 0, 0), 1px 1px 0 rgb(0, 85, 255);
}
#wlcm p {
  font-size: 1.8rem;
  width: 85%;
  margin: 3.5rem;
  line-height: 1.7em;
  color: white;
  text-shadow: -1px -1px 0 rgb(255, 0, 0), 1px -1px 0 rgb(0, 85, 255), -1px 1px 0 rgb(255, 0, 0), 1px 1px 0 rgb(0, 85, 255);
}

#wlcm button {
  padding: 1rem;
  border-radius: 35px;
  border: none;
  background-color: rgb(220, 200, 20);
  color: rgb(35, 35, 35);
  font-size: 2.4rem;
  cursor: pointer;
  width: 20%;
  margin: 1rem;
  text-shadow: -1px -1px 0 rgb(255, 0, 0), 1px -1px 0 rgb(0, 85, 255), -1px 1px 0 rgb(255, 0, 0), 1px 1px 0 rgb(0, 85, 255);
  box-shadow: 1.6px 2px 2.4px rgba(255, 255, 255, 0.308);
}

#wlcm button:active {
  transform: scale(0.96);
}

#wlcm button:hover {
  background-color: rgb(210, 185, 13);
  color: white;
}

</style>
