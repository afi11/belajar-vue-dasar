<template>
    <h1>Luas Segitiga</h1>
    <div><label>Alas</label>
        <input v-model="alas" type="number" name="alas" />
    </div>
    <div><label>Tinggi</label>
        <input v-model="tinggi" type="number" name="tinggi" />
    </div>
    <h3>Luas</h3>
    <h1>{{ luas }}</h1>
</template>

<script>
import { ref } from 'vue'
// Reactive artinya data nya dalam bentuk object
export default {
    name: "App",
    setup() {
        const alas = ref(0);
        const tinggi = ref(0);
        const luas = ref(0);

        console.log(alas);

        return {
            alas,
            tinggi,
            luas
        }
    }
}
</script>