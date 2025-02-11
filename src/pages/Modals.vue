<script setup> 

import { ref } from 'vue';
import Modal from '../comp/Modal.vue';
let modalActive = ref(false);
let modalActive2 = ref(false)
</script>

<template>
    <div class="container mt-3">
        <div class="buttons">
            <button class="button is-primary" @click="modalActive=true">Open Modal</button>
            <button class="button is-warning" @click="modalActive2=true">Open Modal2</button>
        </div>
        
            <Modal :active="modalActive" @click="modalActive=false" url="https://picsum.photos/seed/sigmaboy/1280/960?random=1"> </Modal>
            <Modal :active="modalActive2" @click="modalActive2=false"url="https://picsum.photos/1280/960?r=2"> </Modal>

    </div>
</template>
<style></style>