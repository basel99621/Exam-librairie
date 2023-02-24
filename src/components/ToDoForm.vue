<script setup>
import { ref, defineEmits } from "vue";
// -- donnée réactive pour la saisie du titre
const titre = ref("");
const titreR = ref("");
const prix = ref(0);
const qtestock = ref(0);
const emit = defineEmits(["addC"]);
</script>

<template>
  <body>
    <div id="accueil">
      <form
        id="buttonAjouter"
        @submit.prevent="$emit('addC', titre, prix, qtestock)"
      >
        <input type="text" v-model="titre" placeholder="Nom du livre" />
        <input type="text" v-model="prix" placeholder="Prix du livre" />
        <input
          type="text"
          v-model="qtestock"
          placeholder="La quantité en stock"
        />
        <input class="buttonAjouter" type="submit" value="Ajouter" />
      </form>
      <form class="buttonRechercher" @submit.prevent="$emit('addR', titreR)">
        <input type="text" v-model="titreR" placeholder="Livre Rechercher " />
        <input class="buttoRechercher" type="submit" value="Rechercher" />
      </form>
    </div>
  </body>

  <h1 id="mesLivres">Mes livres</h1>
</template>

<style scoped>
h1 {
  display: flex;
  justify-content: center;
  font-family: Arial, Helvetica, sans-serif; /* Changer la police */
  font-size: 3em; /* Changer la taille de la police */
  text-align: center; /* Centrer le texte */
  color: rgba(255, 64, 0, 0.826); /* Changer la couleur du texte */
  text-shadow: 2px 2px 0 #fff, 4px 4px 0 #999; /* Ajouter un effet d'ombre portée */
  letter-spacing: 0.05em; /* Ajouter un espacement entre les lettres */
  text-transform: uppercase;
}
h1:hover {
  color: rgba(255, 217, 0, 0.751);
}
h1:hover {
  transform: translate(10px, -10px);
  transition: transform 0.5s ease-out;
}
body {
  display: flex;

  align-items: center;
  justify-content: center;
  min-height: 10vh;
  background-color: rgba(255, 255, 255, 0.847);
}

form {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  width: 80%;
  max-width: 800px;
  margin: 1em 0;
}

input {
  margin: 0.5em;
  padding: 0.5em;
  font-size: 1em;
  border: none;
  border-radius: 0.25em;
  box-shadow: 0 0 0.5em rgba(0, 0, 0, 0.1);
}
.buttonAjouter,
.buttoRechercher {
  color: rgba(255, 255, 255, 0.607);
  border: 1px solid #ccc;
  padding: 3px 5px;
  border-radius: 5px;
  text-decoration: none;
  font-size: 16px;
  text-transform: uppercase;
  box-shadow: 0px 0px 5px;
  background: linear-gradient(to bottom right, #4f3c03, #ff545475);
  text-transform: uppercase;
}

.buttoRechercher:hover {
  transform: scale(1.2);
}
.buttonAjouter:hover {
  transform: scale(1.2);
}
div {
  display: flex;
}
</style>
