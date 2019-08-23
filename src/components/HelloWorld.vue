<template>
  <div>
    <img id="barcode"/>
    <div id='imgBox'></div>
    <div @click='handleCreate'>批量生成条形码</div>
  </div>
</template>

<script>
// import barCode from 'jsbarcode'

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
      ]
    }
  },
  mounted () {
    // barCode('#barcode').options({font: 'OCR-B'}).CODE128B(this.numData.ean13, {fontSize: 18, textMargin: 0}).blank(20).render()
  },
  methods: {
    handleCreate () {
      // let _this = this
      // let tempData = _this.numData
      // for (let i in tempData) {
      //   let image = new Image()
      //   image.onload = () => {

      //   }
      //   // console.log(tempData[i])
      // }
      console.log(12)
      let reader = new FileReader()
      let image = new Image()
      reader.onload = function () {
        image.onload = function () {
          console.log(123)
          image.id = 'aa'
          document.getElementById('imgBox').appendChild(image)
        }
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
