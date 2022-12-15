<template>
    <form @submit.prevent="catat">
        <div>
            <label>Pengeluaran</label>
            <input v-model="pengeluaran" type="number" id="pengeluaran" />
        </div>
        <div>
            <label>Keterangan</label>
            <input v-model="keterangan" type="text" id="keterangan" />
        </div>
        <div><button type="submit">Simpan</button></div>
    </form>
</template>

<script>
import {ref} from "vue"

export default {
    name: "FormPengeluaran",
    setup(props, context) {
        const pengeluaran = ref(null);
        const keterangan = ref(null);

        function catat() {
            context.emit('entri-pengeluaran', {
                nominal: pengeluaran.value,
                keterangan: keterangan.value
            });
            pengeluaran.value = null;
            keterangan.value = null;
            document.getElementById("pengeluaran").focus();
        }

        return {
            pengeluaran,
            keterangan,
            catat
        }
    }
}
</script>