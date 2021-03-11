<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Ionic Vue Ion Nav</ion-title>
      </ion-toolbar>
    </ion-header>
    
    <ion-content :fullscreen="true" class="ion-padding">
      <ion-button @click="setOpen(true)">Show Modal With Nav</ion-button>
        <ion-modal
            :is-open="isOpenRef"
            @onDidDismiss="setOpen(false)"
        >
      <base-modal :rootPage="ModalHome"></base-modal>
      </ion-modal>
    </ion-content>

  </ion-page>
</template>

<script lang="ts">
import {
    IonContent,
    IonHeader,
    IonPage,
    IonTitle,
    IonToolbar,
    IonButton,
    IonModal
  } from '@ionic/vue';
import { defineComponent,ref } from 'vue';
import BaseModal from "./BaseModal.vue";
import ModalHome from "./ModalHome.vue";




export default defineComponent({
  name: 'Home',
    setup() {
    const isOpenRef = ref(false);
    const setOpen = (state: boolean) => (isOpenRef.value = state);
    return { isOpenRef, setOpen,  ModalHome };
  }, 
  components: {
    IonContent,
    IonHeader,
    IonPage,
    IonTitle,
    IonToolbar,
    BaseModal,
    IonButton,
    IonModal

  }
});
</script>

<style scoped>
#container {
  text-align: center;
  
  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;
  
  color: #8c8c8c;
  
  margin: 0;
}

#container a {
  text-decoration: none;
}
</style>