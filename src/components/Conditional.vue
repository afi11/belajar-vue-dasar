<template>
    <div>
        <h4>{{ bilangan }}</h4>
        <h4 v-if="genap">Genap</h4>
        <h4 v-if="ganjil">Ganjil</h4>
        <button v-on:click="randomNumber">Generate</button>
    </div>
</template>

<script>
export default {
    name: "ConditionalVue",
    data() {
        return {
            bilangan: 1,
            genap: false,
            ganjil: false
        }
    },
    mounted() {
        this.randomNumber();
    },  
    methods: {
        randomNumber() {
            this.bilangan = Math.floor(Math.random() * 100);
            this.showHide();
        },
        showHide() {
            if(this.bilangan % 2 == 0){
                this.genap = true
                this.ganjil = false
            }else{
                this.ganjil = true
                this.genap = false
            }
        }
    }
}
</script>