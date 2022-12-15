<template>
    <TitlePage title="Pengeluaran Harian" />
    <h2 v-if="warning" class="warning">Pengeluaran Anda Terlalu Banyak</h2>
    <ListPengeluaran v-if="showList" :dataPengeluaran="daftarPengeluaran" />
    <FormPengeluaran @entri-pengeluaran="entriPengeluaran($event)" />
</template>

<script>
import FormPengeluaran from './components-composition-api/FormPengeluaran.vue';
import ListPengeluaran from './components-composition-api/ListPengeluaran.vue';
import TitlePage from './components-composition-api/TitlePage.vue';

import { ref, computed, watch } from 'vue'
// Reactive artinya data nya dalam bentuk object
export default {
    name: "App",
    components: {
        FormPengeluaran,
        ListPengeluaran,
        TitlePage
    },
    setup() {
        const daftarPengeluaran = ref([
            { nominal: 100000, keterangan: "wkwkwkw" }, { nominal: 20000, keterangan: "pretttttttt" }
        ]);

        const warning = ref(false);

        function entriPengeluaran(event) {
            daftarPengeluaran.value.push(event)
        }

        const showList = computed(() => daftarPengeluaran.value.length > 0);
        const totalPengeluaran = computed(() => daftarPengeluaran.value.reduce((accum, item) => accum+parseInt(item.nominal), 0));

        watch(totalPengeluaran, (newValue) => {
            if(newValue > 100000){
                warning.value = true
            }
        });

        return {
            daftarPengeluaran,
            warning,
            entriPengeluaran,
            showList,
            totalPengeluaran
        }
    }
}
</script>