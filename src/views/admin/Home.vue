<template>
  <div>
    <div id="pieContainer" style="width:100%; height:400px"></div>
    <div id="clumnContainer" style="width:100%; height:400px"></div>
  </div>
</template>
<script>
import * as Highcharts from 'highcharts';
export default{
  name:'Home',
  methods:{
    pieFn(){
    Highcharts.chart('pieContainer', {
		chart: {
				plotBackgroundColor: null,
				plotBorderWidth: null,
				plotShadow: false,
				type: 'pie'
		},
		title: {
				text: '舆情关键词分布'
		},
		tooltip: {
				pointFormat: '{series.name}: <b>{point.percentage:.1f}%</b>'
		},
		plotOptions: {
				pie: {
						allowPointSelect: true,
						cursor: 'pointer',
						dataLabels: {
								enabled: true,
								format: '<b>{point.name}</b>: {point.percentage:.1f} %',
								style: {
										color: (Highcharts.theme && Highcharts.theme.contrastTextColor) || 'black'
								}
						}
				}
		},
		series: [{
				name: 'Brands',
				colorByPoint: true,
				data: [{
						name: '中国石油',
						y: 27.0 ,
						sliced: true,
						selected: true
				}, {
						name: '延长石油',
						y: 22.6
				}, {
						name: '大庆石油',
						y: 32.1
				}, {
						name: '天然气分公司',
						y: 18.2
				}]
		}]
});
    },
    columnFn(){
    var chart = Highcharts.chart('clumnContainer',{
    chart: {
        type: 'column'
    },
    title: {
        text: '舆情分布'
    },
    subtitle: {
        text: '数据来源: itying.com'
    },
    xAxis: {
        categories: [
            '一月','二月','三月','四月','五月','六月','七月','八月','九月','十月','十一月','十二月'
        ],
        crosshair: true
    },
    yAxis: {
        min: 0,
        max:300,
        title: {
            text: '舆情数'
        }
    },
    tooltip: {
        // head + 每个 point + footer 拼接成完整的 table
        headerFormat: '<span style="font-size:10px">{point.key}</span><table>',
        pointFormat: '<tr><td style="color:{series.color};padding:0">{series.name}: </td>' +
        '<td style="padding:0"><b>{point.y:.1f} mm</b></td></tr>',
        footerFormat: '</table>',
        shared: true,
        useHTML: true
    },
    plotOptions: {
        column: {
            borderWidth: 0
        }
    },
    series: [{
        name: '正面舆情数',
        data: [49.9, 71.5, 106.4, 129.2, 144.0, 176.0, 135.6, 148.5, 216.4, 194.1, 95.6, 54.4]
    }, {
        name: '负面舆情数',
        data: [83.6, 78.8, 98.5, 93.4, 106.0, 84.5, 105.0, 104.3, 91.2, 83.5, 106.6, 92.3]
    }]
      });
    }
 },
 mounted(){
   this.pieFn();
   this.columnFn();
 }
}
</script>
<style lang="scss">

</style>
