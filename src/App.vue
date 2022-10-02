<template>
<h1 v-bind:class="{secondBackgroundColour: backgroundActive, firstBackgroundColour: !backgroundActive}">Darren's Vue Template</h1>
<div v-if="showList">
<ul>
  <li>{{simpleSum}}</li>
  <li>{{title}}</li>
  <li>{{description}}</li>
  <li>{{content}}</li>
</ul> 
</div>
<button @click="toggleModal(); toggleBackgroundColour()">see list</button>
<Navbar />
<Footer />
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Footer from "./components/Footer.vue";

// Lyfecicle methods
// Ask to create -> Is created at all
// Before create, create, before mount, mount, Before Update, update, Before destroy, destroy

export default {
    name: 'App',
    components: { Navbar, Footer },
    data() {
    return {
    title: 'Jaws',
    description: 'Shark attack movie',
    content: 'Big shark',
    simpleSum: 2 + 2,
    showList: false,
    backgroundActive: true,
     }
 },
 methods: {
  toggleModal() {
    this.showList = !this.showList
  },
  toggleBackgroundColour() {
    this.backgroundActive = !this.backgroundActive;
  }
 }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.secondBackgroundColour {
background: chocolate;
}

.firstBackgroundColour {
background: blue;
}
</style>
