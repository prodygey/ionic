<template>
    <ion-card>
        
        <ion-card-header>
            <ion-card-title>Photo Gallery</ion-card-title>
        </ion-card-header>
        <ion-card-content>
        <div v-if="photos.length === 0" class="empty-gallery">
            <p>No photos captured yet.</p>
            <p>Click the "Take Picture" button to capture a photo.</p>
        </div>
        <ion-grid v-else>
            <ion-row>
                <ion-col
                v-for="(photo, index) in photos" 
                :key="index" 
                size="6"
                size-md="4">
                <ion-card>
                    <ion-img :src="photos" class="gallery-image" />
                </ion-card>
                </ion-col>
            </ion-row>
        </ion-grid>
        </ion-card-content>
    </ion-card>
</template>



<script setup lang="ts">
import {
    IonCard,
    IonCardHeader,
    IonCardTitle,
    IonGrid,
    IonRow,
    IonCol,
} from '@ionic/vue';


defineProps<{ photos: string[] }>();
</script>

<style scoped>
.empty-gallery {
  text-align: center;
  padding: 30px;
  color: #777;
}
.gallery-image {
  width: 100%;
  height: auto;
}
gallery-image::part(image) {
  object-fit: cover;
}
</style>
