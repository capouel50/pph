<template>
<div>
<q-btn :class="{ 'text-cyan-1': !menuOpen, 'text-cyan-4': menuOpen, 'hover-effect': true }" flat label="Gestion">
  <q-menu transition-show="jump-down" transition-hide="jump-up" @show="menuOpen = true" @hide="resetMenu">
    <q-list class="bg-blue-grey-4" dense style="min-width: 100px">
      <q-item clickable v-close-popup class="hover-effect">
        <router-link to="/suppliers/" class="pph-link">
          <q-item-section class="text-cyan-1 hover-effect">Fournisseurs</q-item-section>
        </router-link>
      </q-item>

      <q-item clickable v-close-popup class="hover-effect">
        <router-link to="/matieres-premieres/" class="pph-link">
          <q-item-section class="text-cyan-1 hover-effect">Mat.premières</q-item-section>
        </router-link>
      </q-item>

      <q-item clickable class="hover-effect">
        <q-item-section :class="{ 'text-cyan-1': !submenuOpen2, 'text-cyan-4': submenuOpen2, 'hover-effect': true }">Formules</q-item-section>
        <q-item-section side>
          <q-icon name="keyboard_arrow_right" />
        </q-item-section>

        <q-menu anchor="top end" self="top start" @show="submenuOpen2 = true" @hide="submenuOpen2 = false">
          <q-list class="bg-blue-grey-3">
            <q-item clickable class="hover-effect" v-close-popup>
              <router-link to="/nouvelle-formule/" class="pph-link">
                <q-item-section class="text-cyan-1 hover-effect">Nouvelle formule</q-item-section>
              </router-link>
            </q-item>
            <q-item clickable class="hover-effect" v-close-popup>
              <router-link to="/compositions/" class="pph-link">
                <q-item-section class="text-cyan-1 hover-effect">Compositions</q-item-section>
              </router-link>
            </q-item>
            <q-item clickable class="hover-effect" v-close-popup>
              <q-item-section class="text-cyan-1 hover-effect">En attente de validation</q-item-section>
            </q-item>
          </q-list>
        </q-menu>
      </q-item>

      <q-item clickable class="hover-effect">
        <q-item-section :class="{ 'text-cyan-1': !submenuOpen3, 'text-cyan-4': submenuOpen3, 'hover-effect': true }">stock</q-item-section>
        <q-item-section side>
          <q-icon name="keyboard_arrow_right" />
        </q-item-section>

        <q-menu anchor="top end" self="top start" @show="submenuOpen3 = true" @hide="submenuOpen3 = false">
          <q-list class="bg-blue-grey-3">
            <q-item clickable class="hover-effect" v-close-popup>
              <q-item-section class="text-cyan-1 hover-effect">Préparations</q-item-section>
            </q-item>
            <q-item clickable class="hover-effect" v-close-popup>
              <q-item-section class="text-cyan-1 hover-effect">Matières premières</q-item-section>
            </q-item>
          </q-list>
        </q-menu>
      </q-item>

      <q-item clickable class="hover-effect">
        <q-item-section :class="{ 'text-cyan-1': !submenuOpen4, 'text-cyan-4': submenuOpen4, 'hover-effect': true }">Commandes</q-item-section>
        <q-item-section side>
          <q-icon name="keyboard_arrow_right" />
        </q-item-section>

        <q-menu anchor="top end" self="top start" @show="submenuOpen4 = true" @hide="submenuOpen4 = false">
          <q-list class="bg-blue-grey-3">
            <q-item clickable class="hover-effect" v-close-popup>
              <q-item-section class="text-cyan-1 hover-effect">Produits en attente de commande</q-item-section>
            </q-item>
            <q-item clickable class="hover-effect" v-close-popup>
              <q-item-section class="text-cyan-1 hover-effect">Edition fiche de commande</q-item-section>
            </q-item>
            <q-item clickable class="hover-effect" v-close-popup>
              <q-item-section class="text-cyan-1 hover-effect">Produits en attente de livraison</q-item-section>
            </q-item>
            <q-item clickable class="hover-effect" v-close-popup>
              <q-item-section class="text-cyan-1 hover-effect">Réceptionner une livraison</q-item-section>
            </q-item>
            <q-item clickable class="hover-effect" v-close-popup>
              <q-item-section class="text-cyan-1 hover-effect">Historique des commandes</q-item-section>
            </q-item>
          </q-list>
        </q-menu>
      </q-item>

      <q-item clickable class="hover-effect">
        <q-item-section :class="{ 'text-cyan-1': !submenuOpen5, 'text-cyan-4': submenuOpen5, 'hover-effect': true }">Statistiques</q-item-section>
        <q-item-section side>
          <q-icon name="keyboard_arrow_right" />
        </q-item-section>

        <q-menu anchor="top end" self="top start" @show="submenuOpen5 = true" @hide="submenuOpen5 = false">
          <q-list class="bg-blue-grey-3">
            <q-item clickable class="hover-effect" v-close-popup>
              <q-item-section class="text-cyan-1 hover-effect">Bilan</q-item-section>
            </q-item>
            <q-item clickable class="hover-effect" v-close-popup>
              <q-item-section class="text-cyan-1 hover-effect">Requêtes</q-item-section>
            </q-item>
          </q-list>
        </q-menu>
      </q-item>

      <q-item clickable class="hover-effect">
        <q-item-section :class="{ 'text-cyan-1': !submenuOpen6, 'text-cyan-4': submenuOpen6, 'hover-effect': true }">Tarification</q-item-section>
        <q-item-section side>
          <q-icon name="keyboard_arrow_right" />
        </q-item-section>

        <q-menu anchor="top end" self="top start" @show="submenuOpen6 = true" @hide="submenuOpen6 = false">
          <q-list class="bg-blue-grey-3">
            <q-item clickable class="hover-effect" v-close-popup>
              <q-item-section class="text-cyan-1 hover-effect">Menu1</q-item-section>
            </q-item>
            <q-item clickable class="hover-effect" v-close-popup>
              <q-item-section class="text-cyan-1 hover-effect">Menu2</q-item-section>
            </q-item>
          </q-list>
        </q-menu>
      </q-item>

    </q-list>
  </q-menu>
</q-btn>
</div>
</template>

<script>
export default {
  name: 'GestionBtn',
  data() {
    return {
      menuOpen: false,
      submenuOpen: false,
      submenuOpen2: false,
      submenuOpen3: false,
      submenuOpen4: false,
      submenuOpen5: false,
      submenuOpen6: false,
    };
  },
  methods: {
    resetMenu() {
      this.menuOpen = false;
      this.submenuOpen = false;
      this.submenuOpen2 = false;
      this.submenuOpen3 = false;
      this.submenuOpen4 = false;
      this.submenuOpen5 = false;
      this.submenuOpen6 = false;
    }
  }
}
</script>