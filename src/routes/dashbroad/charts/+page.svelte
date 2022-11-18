<script lang="ts">
	import { init } from 'echarts';
	import { onMount } from 'svelte';

	let chartDom: HTMLElement;
    onMount(()=>{
       const charts =  init(chartDom);
       charts.setOption({
		xAxis: {
			type: 'category',
			data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']
		},
		yAxis: {
			type: 'value'
		},
		series: [
			{
				data: [150, 230, 224, 218, 135, 147, 260],
				type: 'line'
			}
		]
	})

    return ()=> charts.dispose()
    })
</script>

<div bind:this={chartDom} id="echart_core" />

<style>
     #echart_core {
         width:100%;
         height:500px;
     }
</style> 
