<template>
    <div class="v-catalog">
        <h1>Catalog</h1>
        <v-item 
            v-for="product in FilteredProducts"
            :key="product.Id"  
            :product_data="product" 
           
            

           
        />
        
        <v-select
        :options="categories"
        @select="CategoriesSorting"
        :selected="selected"   
        />
      
          <div class="v-cart">
          <h2>Cart</h2>
         <v-cart-item
         v-for="CartDefault in FilteredProducts"
         :key="CartDefault.Id"
         :AddToCart="CartDefault"
         />
          </div>
    </div>
 
</template>

<script>

    import vCartItem from './v-cart-item.vue'
    import vItem from './v-item.vue'
    import vSelect from './v-select.vue'
    export default{
        name: 'v-catalog',
        components: {
            vItem,
            vSelect,
            vCartItem,
            
            
        },
        props: { 
            cart_data:{
                type: Array,
                default () {
                    return []
                }
            }
        },
        data() {
            return {
                categories: [
        {name: 'Men Suit', value: 'me'},
        {name: 'Women Suit', value: 'we'},
        {name: 'Kids Suit', value: 'ki'},
        {name: 'SecondHand Suit', value: 'ss'},
        {name: 'Others', value: 'ot'},
        
      ],
      selected: '',
      ProductSorting: [],
      CartDefault: [],
                 products: [

        {
            image:"1.jpg",
            name:"Suit1",
            price: 100,
            Id: "S1",
            available:true,
            category: 'Men Suit',
            inCart: false,

        },
        {
            image:"2.jpg",
            name:"Suit2",
            price: 120,
            Id: "S2",
            available:true,
            category: 'Men Suit',
            inCart: false,

        },
        {
           image:"3.jpg",
            name:"Suit3",
            price: 130,
            Id: "S3",
            available:true,
            category: 'Men Suit',
            inCart: false,

        },
        {
            image:"4.jpg",
            name:"Suit4",
            price: 140,
            Id: "S4",
            available:true,
            category: 'Men Suit',
            inCart: false,

        },
        {
            image:"5.jpg",
            name:"Suit5",
            price: 150,
            Id: "S5",
            available:true,
            category: 'Women Suit',
            inCart: false,

        },
        {
            image:"6.png",
            name:"Suit6",
            price: 160,
            Id: "S6",
            available:true,
            category: 'Women Suit',
            inCart: false,

        },
        {
            image:"7.jpg",
            name:"Suit7",
            price: 170,
            Id: "S7",
            available:true,
            category: 'Women Suit',
            inCart: false,

        },
        {
            image:"8.jpg",
            name:"Suit8",
            price: 180,
            Id: "S8",
            available:true,
            category: 'Women Suit',
            inCart: false,
    } ],
                 
    
            }
        },
        computed: {
            FilteredProducts() {
                if(this.ProductSorting.length){
                    return this.ProductSorting
                 }else{
                    return this.products
                 }
            },

        },
       methods: {
          CategoriesSorting(category) {
        this.ProductSorting = [];
        let vm = this;
      this.FilteredProducts.map(function(item){
          if(item.category=== category.name){
            vm.ProductSorting.push(item);
            }
        })
         },
         //Если товар не в корзине то есть inCart является fasle то при клике на кнопку Add to Cart после ввода метода push(product) то в таком случае товар должен попасть в корзину но почему он не попдает??? 
         AddingToCart(inCart){
             this.CartDefault = [];
             let cm = this;
             this.products.map(function(CartItem){
                 if(CartDefault.length){
                 }
             })
         }
         
        
         }

           
       
    
    }
</script>

<style>
    .v-calatog{
        max-width: 200px;
        max-block-size: 100px;
        flex-wrap: wrap;
        justify-content: space-between;
        align-items: center;
        
    }

</style>>