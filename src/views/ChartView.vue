<template>
  <section>
    <h2>月度销售图</h2>
    <div ref="chart" class="chart"></div>
  </section>
</template>

<script>
import * as echarts from 'echarts'

export default {
  name: 'ChartView',
  data() {
    return {
      chart: null
    }
  },
  mounted() {
    this.initChart()
    window.addEventListener('resize', this.handleResize)
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.handleResize)
    if (this.chart) {
      this.chart.dispose()
      this.chart = null
    }
  },
  methods: {
    initChart() {
      this.chart = echarts.init(this.$refs.chart)
      this.chart.setOption({
        tooltip: {},
        xAxis: {
          type: 'category',
          data: ['1月', '2月', '3月', '4月', '5月', '6月']
        },
        yAxis: {
          type: 'value'
        },
        series: [
          {
            name: '销售额',
            type: 'bar',
            data: [120, 200, 150, 80, 70, 110],
            itemStyle: {
              color: '#409EFF'
            }
          }
        ]
      })
    },
    handleResize() {
      if (this.chart) {
        this.chart.resize()
      }
    }
  }
}
</script>

<style scoped>
.chart {
  width: 100%;
  height: 420px;
  border: 1px solid #ebeef5;
  border-radius: 8px;
}
</style>
