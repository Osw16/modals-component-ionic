<template>
    <ion-page>
        <ion-header :translucent="true">
            <ion-toolbar>
                <ion-buttons slot="start" >
                    <ion-button @click="goBack">BACK</ion-button>
                </ion-buttons>
                <ion-title>MODAL HOME DETAILS</ion-title>
            </ion-toolbar>
        </ion-header>
        <ion-content class="ion-padding">
            <h2>MODAL DETAIL</h2>
        </ion-content>
    </ion-page>
</template>

<script>
import { defineComponent } from "vue";
import {
        IonContent,
        IonHeader,
        IonPage,
        IonTitle,
        IonToolbar,
        IonButtons,
        IonButton, 
     } from "@ionic/vue";
export default defineComponent ({
    name: "ModalHomeDetail",
    components:{
        IonContent,
        IonHeader,
        IonPage,
        IonTitle,
        IonToolbar,
        IonButtons,
        IonButton,
    },
    props:["modalNav"],
    setup(props){
        const goBack =()=>{
            const nav = props.modalNav.value;
            nav.pop();
        };
        return{
            goBack
        };
    }
});
</script>

<style>

</style>