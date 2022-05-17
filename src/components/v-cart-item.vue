<template >
    <div class="v-cart-item">
        
    </div>
</template>
<script>
export default {
    name: 'v-cart-item',
    components:{


    },
    props:{
            AddToCart:{
                type: Array,
                default(){
                    return []
                }
            }

    },
    data() {
        return {
            
        }

    },
    computed: {

    },
    methods:{
        AddToCard(){
            this.$emit('AddToCard', this.AddToCart)
        }
    },
    
}
</script>
<style >
    
</style>