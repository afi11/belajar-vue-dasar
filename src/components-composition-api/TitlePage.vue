<template>
    <h1>{{ title }}</h1>
</template>

<script>
export default {
    name: "TitlePage",
    props: {
        title: String,
    }
}
</script>
<style scoped>
h1 {
    color: #ef2828;
}
</style>