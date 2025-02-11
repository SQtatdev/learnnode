<script setup>
import Tabs from './comp/Tabs.vue';
import { ref } from 'vue';

import ToDo from './pages/ToDo.vue';
import Modals from './pages/Modals.vue';

let titles = [
    'ToDO',
    'Modals',
];

let contents = [
    ToDo,
    Modals,
]

let activeTab = ref(0);
function change(key){
    activeTab.value = key;
}

</script>
<template>
    <Tabs :items="titles" @change="change"></Tabs>
    <component :is="contents[activeTab]"></component>

</template>