<template>
    <div class="button-scene">
      <button @click="$emit('alternatePhrase', 1)">ENRERE</button>
      <button @click="$emit('alternatePhrase', 2)">ENDAVANT</button>
    </div>
    <div class="button-back">
      <button @click="$emit('alternatePlotMenu')">TORNAR</button>
    </div>
  </template>

<script>
export default {
  name: "Botons",
};
</script>

<style>
.button-scene {
  text-align: center;
  transform: translateY(2.5rem)
}

.button-back {
  position: relative;
  text-align: center;
  transform: translateY(30rem);
}

.button-scene button, .button-back button {
  font-size: 1.4rem;
  font-weight: 700;
  padding: .9rem;
  width: 15%;
  border-radius: 25px;
  margin: 1rem 5rem 1rem 5rem;
  border: none;
  color: white;
  background-color: rgb(45, 70, 236);
  cursor: pointer;
}

.button-scene button:active, .button-back button:active{
  transform: scale(0.98);
  background-color: rgba(0, 34, 255, 0.775);
  color: rgb(0, 0, 0);
}

.button-back button {
  font-size: 1.4rem;
  
}

button:hover {
  background-color: rgb(0, 34, 255);
  color: white;
}
</style>