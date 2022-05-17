<template>
    <div class="v-item">
        <img class="v-item__image" :src=" require('../assets/images/' + product_data.image) " alt="img">
        <p class="Item_name">{{product_data.name}}</p>
        <p class="Item_price">Price: {{product_data.price}}</p>
        
        <button 
        class="Item_cart"
        @click="Cart"
        >Add to cart</button>


    </div>
</template>

<script>

    export default{
        name: 'v-item',
        components: {
            
        },
        props: {
            product_data: {
                type: Object,
                default() {
                    return {}
                }
            }
        },
        data() {
            return {
                
            }
        },
        computed: {},
        methods: { 
            Cart()
            {
                this.$emit('Cart',this.product_data);
            }
        },
    
    }
</script>

<style>
    .v-item{
        flex-basis: 25%;
        box-shadow: 0 0 8px 0 #808080;
        padding: 16px;
        margin-bottom: 16px;
        width: 25%;
        

    }
    .v-item__image{
        width: 70px;

    }

</style>>