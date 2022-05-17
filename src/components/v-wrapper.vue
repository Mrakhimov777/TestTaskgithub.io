<template>
    <div class="v-wrapper">
        <v-catalog
        
        />
        
    </div>
</template>

<script>
    import vCatalog from './v-catalog.vue'

    export default{
        name: 'v-wrapper',
        components: {
            vCatalog,
            
        },
        props: {

        },
        data() {
            return {
                
            }
        },
        computed: {},
        
    
    }
</script>

<style>
    .v-wrapper {
        max-width: 900px;
        margin: 0 auto;
    }

</style>



