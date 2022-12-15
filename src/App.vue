<template>
  <DeklaratifRendering />
  <!-- Ganti Materi -->
  <EventListener />
  <!-- Ganti Materi -->
  <TwoWayDataBinding />
  <!-- Ganti Materi -->
  <ConditionalVue />
  <!-- Ganti Materi -->
  <LoopsVue />
  <!-- Ganti Materi (Komponen Static Props) -->
  <TitleComponent title="Ini Komponen dg Static Props" />
  <!-- Ganti Materi (Komponen Dynamic Props)  -->
  <!-- Computed & Watch -->
  <h2 v-if="warning" class="warning">Pengeluaran Anda Terlalu Banyak</h2>
  <ListPengeluaran v-if="showList" :dataPengeluaran="daftarPengeluaran" />
  <!-- Ganti Materi (Emit) -->
  <FormPengeluaran @entri-pengeluaran="entriPengeluaran($event)" />
</template>

<script>
import DeklaratifRendering from "./components/DeklaratifRendering.vue";
import EventListener from "./components/EventListener.vue";
import TwoWayDataBinding from "./components/TwoWayDataBinding.vue";
import ConditionalVue from "./components/Conditional.vue";
import LoopsVue from "./components/Loops.vue"
// New Part
import TitleComponent from "./components/TitleComponent.vue";
import ListPengeluaran from "./components/ListPengeluaran.vue";
import FormPengeluaran from "./components/FormPengeluaran.vue";

export default {
  name: 'App',
  components: {
    DeklaratifRendering,
    EventListener,
    TwoWayDataBinding,
    ConditionalVue,
    LoopsVue,
    TitleComponent,
    ListPengeluaran,
    FormPengeluaran
  },
  data() {
    return {
      daftarPengeluaran: [
        {nominal: 100000, keterangan: "wkwkwkw"}, {nominal: 20000, keterangan: "pretttttttt"}
      ],
      warning: false
    }
  },
  methods: {
    entriPengeluaran(event) {
      this.daftarPengeluaran.push(event)
    }
  },
  // untuk menghitung & mengurangi logic di template
  computed: {
    showList: function() {
      return this.daftarPengeluaran.length > 0;
    },
    totalPengeluaran: function() {
      return this.daftarPengeluaran.reduce((accum, item) => accum+parseInt(item.nominal), 0);
    }
  },
  // untuk menampilkan data based on kondisi tertentu
  watch: {
    totalPengeluaran: function(val) {
      if(val > 100000){
        this.warning = true;
      }
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
