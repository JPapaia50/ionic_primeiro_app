<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title size="large">Galeria de Foto</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Galeria de Foto</ion-title>
        </ion-toolbar>
      </ion-header>
      <ion-fab vertical="bottom" horizontal="center" slot="fixed">
        <ion-fab-button>
          <ion-icon :icon="camera" @click="takePhoto()"></ion-icon>
        </ion-fab-button>
      </ion-fab>


    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
import { camera , trash, close} from 'ionicons/icons';
import { usePhotoGallery } from '@/composable/usePhotoGallery'

export default defineComponent({
  name: 'Tab1Page',
  components: { IonHeader, IonToolbar, IonTitle, IonContent, IonPage },
  setup() {
    const { takePhoto } = usePhotoGallery();
    return {
      takePhoto,
      camera,trash, close
    }
  }
});
</script>
