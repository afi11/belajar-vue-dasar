<template>
    <table>
        <tr v-for="day in days" v-bind:key="day">
            <td>{{ day }}</td>
        </tr>
    </table>
</template>

<script>
export default {
    name: "LoopsVue",
    data() {
        return {
            days: ["Senis", "Selasa", "Rabu", "Kamis", "Jumat", "Sabtu", "Minggu"]
        }
    }
}
</script>