<script setup>
<<<<<<< Updated upstream

import { ref } from 'vue';
import RouterTabs from './comp/RouterTabs.vue';
import { RouterView } from 'vue-router';

</script>
<template>

<RouterTabs>
    
</RouterTabs>

<RouterView>

</RouterView>

=======
import { ref } from 'vue';
import RouterTabs from './comp/RouterTabs.vue';


</script>
<template>
    <RouterTabs></RouterTabs>
    <div class="container">
        <section class="section">
            <Suspense>
                <RouterView></RouterView>
            </Suspense>
        </section>
    </div>
>>>>>>> Stashed changes
</template>