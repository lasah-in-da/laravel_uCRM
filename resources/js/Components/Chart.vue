<script setup>
import { Chart, registerables } from "chart.js";
import { BarChart } from "vue-chart-3";
import { reactive,computed } from "vue"


const labels = computed(() => props.data.labels);
const totals = computed(() => props.data.totals);


const props = defineProps({
    "data" : Object
})

const barData = reactive({
    labels: labels,
    datasets: [
        {
            label: "売上",
            data:
                totals,
            backgroundColor: "rgb(75, 192, 192)",
            tension: 0.1,
        }
    ]
}) 




Chart.register(...registerables);
</script>

<template>
    <div v-show="props.data">
        <BarChart :chartData="barData" />
    </div>
</template>