<template>
  <div>
<!--    <img id="barcode" ref="imgBarCode" />-->
<!--    <div id='imgBox'></div>-->
    <button @click='handleCreate'>批量生成条形码</button>
    <div style="display: none;" v-for="(item, index) in imgBox" :key="index"><img :src="item" alt=""></div>
  </div>
</template>

<script>
import barCode from 'jsbarcode'

export default {
  name: 'HelloWorld',
  data () {
    return {
      numData: [
        '2019082342773-1-0',
        '2019082342773-1-1',
        '2019082342773-1-2',
        '2019082342773-1-3',
        '2019082342773-1-4'
      ],
      imgBox: []
    }
  },
  mounted () {
    // barCode('#barcode').options({font: 'OCR-B'}).CODE128B(this.numData[0], {fontSize: 18, textMargin: 0}).blank(20).render()
  },
  methods: {
    handleCreate () {
      let _this = this
      let arr = _this.imgBox
      let tempData = _this.numData
      for (let i in tempData) {
        let canvas = document.createElement('canvas')
        barCode(canvas).options({font: 'OCR-B'}).CODE128B(tempData[i], {
          fontSize: 18,
          textMargin: 0
        }).blank(20).render()
        arr.push(canvas.toDataURL('image/png'))
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
