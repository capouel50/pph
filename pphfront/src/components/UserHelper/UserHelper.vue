<template>
  <q-fab glossy class="btn-grey-primary-pph" icon="help" direction="left">
    <q-fab-action glossy class="btn-grey-primary-pph" @click="toggleForm" icon="contact_support" />
    <q-fab-action glossy class="btn-grey-primary-pph" @click="onClick" icon="play_lesson" />
  </q-fab>
</template>

<script>
import { mapState } from 'vuex';

export default {
  name: "UserHelper",

  computed: {
    ...mapState('contact', ['showForm'])
  },

  methods: {
    toggleForm() {
      this.$store.commit('contact/SET_SHOW_FORM', !this.showForm);
    },

    onClick() {
      // Autre action pour le bouton 'play_lesson' si nécessaire
    }
  }
};
</script>


<style scoped>
.q-fab {
  position: fixed;
  bottom: 10px; /* ou la marge que vous souhaitez depuis le bas de l'écran */
  right: 10px; /* ou la marge que vous souhaitez depuis le côté droit de l'écran */
  z-index: 10000; /* assurez-vous qu'il passe par-dessus les autres éléments, ajustez si nécessaire */
}
</style>