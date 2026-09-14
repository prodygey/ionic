<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Photo GAllery</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content class="ion-padding">
      <CameraComponent @photoCaptured="addPhoto" />
      <PhotoGalCom :photos="photos" />
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import CameraComponent from '@/components/cameraComponent.vue';
import PhotoGalCom from '@/components/PhotoGalCom.vue';
import { 
  IonContent, 
  IonHeader, 
  IonPage, 
  IonTitle, 
  IonToolbar 
  } from '@ionic/vue';

  const photos = ref<string[]>([]);
  const addPhoto = (photo: string) => {
    photos.value.unshift(photo);
  };
</script>
<!--
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
-->