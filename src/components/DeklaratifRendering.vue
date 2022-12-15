<template>
    <h1>Hello World</h1>
    <h4>Project Vue Pertama Saya</h4>
    <h4>Nama Saya {{ nama }}</h4>
    <h4>Umur Saya {{ umur }}</h4>
</template>

<script>
export default {
    name: "DeklaratifRendering",
    data() {
        return {
            nama: "Mukidi",
            umur: 22
        }
    },
    mounted() {
        this.umur = this.umur + 1
    }
}
</script>