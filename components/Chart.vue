<script setup lang="ts">
import chart from 'chart.js/auto';

const labels = [
    'Januari',
    'Februari',
    'March',
    'April',
    'May',
    'June',

    ];


const data ={
    labels:labels,
    datasets:[{
    label: 'pengunjung',
    data: [6, 8, 10, 9, 9,3],
    backgroundColor:[
        'rgb(0,0,255)',
        'rgb(75,0,130)',
        'rgb(0,255,0)',
        'rgb(255,255,0)',
        'rgb(255,0,0)',
        'rgb(255,0,255)'
    ],
    }]
};

    const config = {
        type: 'bar',
        data: data,
        Options : {}
    };

    onMounted(() => {
        const myChart = new chart (
            document.getElementById('myChart'),
            config
        );
    })
</script>

<template>
    <div>
        <canvas id="myChart"></canvas>
    </div>
</template>