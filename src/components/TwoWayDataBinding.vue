<template>
    <h1>Penggunaan V Model</h1>
    <h4>{{ message }}</h4>
    <input v-model="message" />
</template>

<script>
export default {
    name: "TwoWayDataBinding",
    data() {
        return {
            message: ""
        }
    }
}
</script>