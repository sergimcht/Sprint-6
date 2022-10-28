<template>
  <p id="SceneText" v-for="item, index in plot" :key="index" :class="{ activePhrase: index === currentPhrase }">
  {{ item.txt }}</p>
</template>

<script>
export default {
    name: "Scene",
    props: ['plot', 'currentPhrase'],
}
</script>

<style>
#SceneText {
  text-align: center;
  font-weight: 700;
  font-size: 1.5rem;
  margin: 0 5rem 2rem 5rem;
  padding: .85rem;
  border-radius: 20px;
  text-shadow: 5px 5px 5px rgb(0, 0, 0);
  color: rgb(255, 255, 255);
  background-color: rgba(45, 70, 236, 0.45);
}

.activePhrase {
  outline: solid 5px rgb(255, 255, 255);
}

</style>
