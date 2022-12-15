<template>
    <h1>Deret Bilangan Ganjil</h1>
    <h4>{{ bilangan }}</h4>
    <button v-on:click="next">Next</button>
</template>

<script>
export default {
    name: "EventListener",
    data() {
        return {
            bilangan: 1
        }
    },
    methods: {
        next(){
            this.bilangan += 2
        }
    }
}
</script>