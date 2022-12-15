<template>
    <h1>Luas Segitiga</h1>
    <div><label>Alas</label>
        <input v-model="state.alas" type="number" name="alas" />
    </div>
    <div><label>Tinggi</label>
        <input v-model="state.tinggi" type="number" name="tinggi" />
    </div>
    <h3>Luas</h3>
    <h1>{{ state.luas }}</h1>
</template>

<script>
import { reactive } from 'vue'
// Reactive artinya data nya dalam bentuk object
export default {
    name: "App",
    setup() {
        const state = reactive({
            alas: 0,
            tinggi: 0,
            luas: 0
        });


        return {
            state
        }
    }
}
</script>