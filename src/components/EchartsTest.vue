<template>
  <div id="myChart" :style="{width: '500px', height: '500px'}" />
</template>

<script>
import 'echarts/map/js/china' // 这个是js引用
// import chinaJson from 'echarts/map/json/china.json'
// import HKJson from 'echarts/map/json/province/xianggang.json'
import testJson from 'echarts/map/json/test/echarts_test.json'
export default {
  name: 'EchartsTest',
  data() {
    return {
    }
  },
  mounted() {
    // this.drawLine()
    this.test()
  },
  methods: {
    drawLine() {
      // 基于准备好的dom，初始化echarts实例
      const myChart = this.$echarts.init(document.getElementById('myChart'))
      // 绘制图表
      // myChart.setOption({
      //   title: { text: '在Vue中使用echarts' },
      //   tooltip: {},
      //   xAxis: {
      //     data: ['衬衫', '羊毛衫', '雪纺衫', '裤子', '高跟鞋', '袜子']
      //   },
      //   yAxis: {},
      //   series: [{
      //     name: '销量',
      //     type: 'bar',
      //     data: [5, 20, 36, 10, 10, 20]
      //   }]
      // })
      // $.get('data.json').done(function(data) {
      //   myChart.setOption({
      //     title: {
      //       text: '异步数据加载示例'
      //     },
      //     tooltip: {},
      //     legend: {
      //       data: ['销量']
      //     },
      //     xAxis: {
      //       data: ['衬衫', '羊毛衫', '雪纺衫', '裤子', '高跟鞋', '袜子']
      //     },
      //     yAxis: {},
      //     series: [{
      //       name: '销量',
      //       type: 'bar',
      //       data: [5, 20, 36, 10, 10, 20]
      //     }]
      //   })
      // })
      this.$axios.get('http://mock-api.com/vzM9NwzG.mock/get/data').then(response => {
        myChart.setOption(response.data)
      }
      )
    },
    test() {
      const myChart = this.$echarts.init(document.getElementById('myChart'))
      // $.get(ROOT_PATH + 'data/asset/geo/HK.json', function(geoJson) {
      //   myChart.hideLoading()
      //
      //   echarts.registerMap('HK', geoJson)
      //
      //   myChart.setOption({
      //     title: {
      //       text: '香港18区人口密度 （2011）',
      //       subtext: '人口密度数据来自Wikipedia',
      //       sublink: 'http://zh.wikipedia.org/wiki/%E9%A6%99%E6%B8%AF%E8%A1%8C%E6%94%BF%E5%8D%80%E5%8A%83#cite_note-12'
      //     },
      //     tooltip: {
      //       trigger: 'item',
      //       formatter: '{b}<br/>{c} (p / km2)'
      //     },
      //     toolbox: {
      //       show: true,
      //       orient: 'vertical',
      //       left: 'right',
      //       top: 'center',
      //       feature: {
      //         dataView: { readOnly: false },
      //         restore: {},
      //         saveAsImage: {}
      //       }
      //     },
      //     visualMap: {
      //       min: 800,
      //       max: 50000,
      //       text: ['High', 'Low'],
      //       realtime: false,
      //       calculable: true,
      //       inRange: {
      //         color: ['lightskyblue', 'yellow', 'orangered']
      //       }
      //     },
      //     series: [
      //       {
      //         name: '香港18区人口密度',
      //         type: 'map',
      //         mapType: 'HK', // 自定义扩展图表类型
      //         label: {
      //           show: true
      //         },
      //         data: [
      //           { name: '中西区', value: 20057.34 },
      //           { name: '湾仔', value: 15477.48 },
      //           { name: '东区', value: 31686.1 },
      //           { name: '南区', value: 6992.6 },
      //           { name: '油尖旺', value: 44045.49 },
      //           { name: '深水埗', value: 40689.64 },
      //           { name: '九龙城', value: 37659.78 },
      //           { name: '黄大仙', value: 45180.97 },
      //           { name: '观塘', value: 55204.26 },
      //           { name: '葵青', value: 21900.9 },
      //           { name: '荃湾', value: 4918.26 },
      //           { name: '屯门', value: 5881.84 },
      //           { name: '元朗', value: 4178.01 },
      //           { name: '北区', value: 2227.92 },
      //           { name: '大埔', value: 2180.98 },
      //           { name: '沙田', value: 9172.94 },
      //           { name: '西贡', value: 3368 },
      //           { name: '离岛', value: 806.98 }
      //         ],
      //         // 自定义名称映射
      //         nameMap: {
      //           'Central and Western': '中西区',
      //           'Eastern': '东区',
      //           'Islands': '离岛',
      //           'Kowloon City': '九龙城',
      //           'Kwai Tsing': '葵青',
      //           'Kwun Tong': '观塘',
      //           'North': '北区',
      //           'Sai Kung': '西贡',
      //           'Sha Tin': '沙田',
      //           'Sham Shui Po': '深水埗',
      //           'Southern': '南区',
      //           'Tai Po': '大埔',
      //           'Tsuen Wan': '荃湾',
      //           'Tuen Mun': '屯门',
      //           'Wan Chai': '湾仔',
      //           'Wong Tai Sin': '黄大仙',
      //           'Yau Tsim Mong': '油尖旺',
      //           'Yuen Long': '元朗'
      //         }
      //       }
      //     ]
      //   })
      // })
      //
      // this.$axios.get('http://mock-api.com/vzM9NwzG.mock/get/data/map-test').then(response => {
      //   // myChart.hideLoading()
      //   // console.log(response.data)
      //   this.$echarts.registerMap('HK', response.data)
      //   myChart.setOption(response.data)
      // })

      // this.$echarts.registerMap('HK', HKJson)

      // myChart.setOption({
      //   title: {
      //     text: '香港18区人口密度 （2011）',
      //     subtext: '人口密度数据来自Wikipedia',
      //     sublink: 'http://zh.wikipedia.org/wiki/%E9%A6%99%E6%B8%AF%E8%A1%8C%E6%94%BF%E5%8D%80%E5%8A%83#cite_note-12'
      //   },
      //   tooltip: {
      //     trigger: 'item',
      //     formatter: '{b}<br/>{c} (p / km2)'
      //   },
      //   toolbox: {
      //     show: true,
      //     orient: 'vertical',
      //     left: 'right',
      //     top: 'center',
      //     feature: {
      //       dataView: { readOnly: false },
      //       restore: {},
      //       saveAsImage: {}
      //     }
      //   },
      //   visualMap: {
      //     min: 800,
      //     max: 50000,
      //     text: ['High', 'Low'],
      //     realtime: false,
      //     calculable: true,
      //     inRange: {
      //       color: ['lightskyblue', 'yellow', 'orangered']
      //     }
      //   },
      //   series: [
      //     {
      //       name: '香港18区人口密度',
      //       type: 'map',
      //       mapType: 'HK', // 自定义扩展图表类型
      //       label: {
      //         show: true
      //       },
      //       data: [
      //         { name: '中西区', value: 20057.34 },
      //         { name: '湾仔', value: 15477.48 },
      //         { name: '东区', value: 31686.1 },
      //         { name: '南区', value: 6992.6 },
      //         { name: '油尖旺', value: 44045.49 },
      //         { name: '深水埗', value: 40689.64 },
      //         { name: '九龙城', value: 37659.78 },
      //         { name: '黄大仙', value: 45180.97 },
      //         { name: '观塘', value: 55204.26 },
      //         { name: '葵青', value: 21900.9 },
      //         { name: '荃湾', value: 4918.26 },
      //         { name: '屯门', value: 5881.84 },
      //         { name: '元朗', value: 4178.01 },
      //         { name: '北区', value: 2227.92 },
      //         { name: '大埔', value: 2180.98 },
      //         { name: '沙田', value: 9172.94 },
      //         { name: '西贡', value: 3368 },
      //         { name: '离岛', value: 806.98 }
      //       ],
      //       // 自定义名称映射
      //       nameMap: {
      //         'Central and Western': '中西区',
      //         'Eastern': '东区',
      //         'Islands': '离岛',
      //         'Kowloon City': '九龙城',
      //         'Kwai Tsing': '葵青',
      //         'Kwun Tong': '观塘',
      //         'North': '北区',
      //         'Sai Kung': '西贡',
      //         'Sha Tin': '沙田',
      //         'Sham Shui Po': '深水埗',
      //         'Southern': '南区',
      //         'Tai Po': '大埔',
      //         'Tsuen Wan': '荃湾',
      //         'Tuen Mun': '屯门',
      //         'Wan Chai': '湾仔',
      //         'Wong Tai Sin': '黄大仙',
      //         'Yau Tsim Mong': '油尖旺',
      //         'Yuen Long': '元朗'
      //       }
      //     }
      //   ]
      // })
      this.$echarts.registerMap('test', testJson)
      myChart.setOption({
        tooltip: {
          trigger: 'item',
          formatter: '{b}<br/>{c} (p / km2)'
        },
        toolbox: {
          show: true,
          orient: 'vertical',
          left: 'right',
          top: 'center',
          feature: {
            dataView: { readOnly: false },
            restore: {},
            saveAsImage: {}
          }
        },
        visualMap: {
          min: 400,
          max: 1500,
          text: ['High', 'Low'],
          realtime: false,
          calculable: true,
          inRange: {
            color: ['lightskyblue', 'yellow', 'orangered']
          }
        },
        series: [{
          type: 'map',
          map: 'test',
          data: [
            { name: '2015-37020220157004青岛市盲校用', value: 790.774005737 },
            { name: '2015青岛晟世建筑科技工程有限公司', value: 438.565558782 },
            { name: '2015深圳华信天线技术有限公司（华', value: 481.553620248 },
            { name: '2015西诺墨新机器人（荣泰西诺）', value: 465.811892695 },
            { name: '2015中纺亿联东边土地(挂牌)2014.1', value: 1389.80267163 },
            { name: '20150121798青岛港湾职业技术学院6', value: 1186.12012265 },
            { name: '20150121797青岛港湾职业技术学院9', value: 489.234295918 }
          ],
          nameMap: {
            '1': '2015-37020220157004青岛市盲校用',
            '2': '2015青岛晟世建筑科技工程有限公司',
            '3': '2015深圳华信天线技术有限公司（华',
            '4': '2015西诺墨新机器人（荣泰西诺）',
            '5': '2015中纺亿联东边土地(挂牌)2014.1',
            '6': '20150121798青岛港湾职业技术学院6',
            '7': '20150121797青岛港湾职业技术学院9'
          }
        }]
      })

      // this.$echarts.registerMap('china', chinaJson) // 如果是js引入就不需要这一行了
      // // 绘制地图
      // myChart.setOption({
      //   geo: {
      //     map: 'china'
      //   }
      // })
    }
  }
}

</script>

<style scoped>

</style>
