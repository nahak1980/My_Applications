<template>
    <div>
        {{ kattify }}
        <input v-model="newCat" v-on:keyup.enter="addKitty">
        <button v-on:click="addKitty"> Add </button>
        <br>
        <br>
        <ul>
            <li v-for="cat in cats" :key="cat">{{ cat }}</li>
        </ul>
        <b-button variant="success">Success</b-button>
    </div>
</template>
<script>
export default {
    name: 'use-function',
    data(){
        return{
            cats: [
                'Meew',
                'laku',
                'saku',
                'tiku'
            ],
            newCat: ''
        }
    },
    methods:{
        addKitty(){
            this.cats.push(this.newCat);
            return this.newCat = '';
        }
    },
    // filters: {
    //     capitalize: function(value){
    //         return value.toUpperCase();
    //     },
    //     adds: function(value){
    //     return value + 'S';
    //     }
    // },
    computed: {
        kattify: function(){
             return this.newCat + 'Y';
            // if(this.newCat.length > 1) {
            //     return this.newCat + 'Y';
            // }
        }
    }
    

}
</script>