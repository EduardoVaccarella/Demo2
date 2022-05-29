<template>
    <div class="container-fluid border-top border-bottom ms_navbar">
        <div class="d-flex justify-content-between align-items-center container py-4 gapx-1">
            <logo-component/>
            <searchbar-component/>
            <loggedpill-component/>
        </div>
    </div>
</template>

<script>
import LogoComponent from './partials/LogoComponent.vue';
import LoggedpillComponent from './partials/LoggedpillComponent.vue';
import SearchbarComponent from './partials/SearchbarComponent.vue';

    export default {
  components: { LoggedpillComponent, LogoComponent, SearchbarComponent }
    }
</script>

<style lang="scss" scoped>
    
    .ms_navbar {
        position: sticky;
    }

</style>