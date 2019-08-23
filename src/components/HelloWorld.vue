<template>
  <div>
    <img id="barcode"/>
  </div>
</template>

<script>
import barCode from 'jsbarcode'

export default {
  name: 'HelloWorld',
  data () {
    return {
      numData: {
        ean13: 1234567890128
      }
    }
  },
  mounted () {
    barCode('#barcode').options({font: 'OCR-B'}).EAN13(this.numData.ean13, {fontSize: 18, textMargin: 0}).blank(20).render()
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
