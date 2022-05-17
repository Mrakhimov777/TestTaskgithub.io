<template>
    <div class='v-select'>
      <p class="title">{{selected}}</p>
      <div class="options">
          <p
            v-for="option in options"
            :key="option.value"
            @click="selectOption(option)"  
          >
            {{option.name}}   
          </P>

      </div>  
    </div>
</template>

<script>

export default {
    name: "v-select",
    props: {
        options: {
            type: Array,
            default() {
                return []
            }
        },
        
    },
    data() {
        return {
            
        }
    },
    methods: {
        selectOption(option) {
            this.$emit('select', option)
           
        }
    }
}
</script>
<style>    
    .options {
        
        box-shadow: 0 0 5px 0 #9a9a9a;
        position: absolute;
        top: 30px;
        left: 20px;
        width: 25%;
        cursor: pointer;
        

    }
    .options p:hover {
        background: #e7e7e7;
    }

</style>
