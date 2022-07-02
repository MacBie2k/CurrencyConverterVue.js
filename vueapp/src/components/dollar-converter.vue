<template>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.0-beta1/dist/css/bootstrap.min.css"
        rel="stylesheet" integrity="sha384-0evHe/X+R7YkIZDRvuzKMRqM+OrBnVFBL6DOitfPri4tjfHxaWutUpFmBp4vmVor" crossorigin="anonymous">
  <body>
  <div v-if="rate != null" id="dollarRate" class="container-sm">
      <div class="form-group">
        <h1 >Current USD rate: {{rate}} PLN</h1>

        <label>PLN</label>
        <input type="number" min="0" class="form-control" v-model="pln"  placeholder="Enter PLN">

      </div>
      <div>
        <button @click="convertToDollars" class="btn btn-primary">Convert</button>
      </div>
      <div class="form-group">
        <label >USD</label>
        <input type="number" class="form-control" v-model="usd"  id="exampleInputPassword1" placeholder="Check USD" readonly>
      </div>
  </div>
  <h1 v-else> Can't get current rate. Please try later!</h1>
  </body>
</template>

<script>

import  axios from  'axios';

export default {
name:"dollarRate",
  data () {
    return {
      rate: null,
      usd: null,
      pln: null,
    }
  },
  methods: {
  convertToDollars()
  {
    this.usd = (this.pln/this.rate).toFixed(2);
  }
  },
  mounted() {
    axios
        .get('https://localhost:44326/api/Rate/usd')
        .then(response => this.rate = response.data.mid)

  }

}
</script>

<style scoped>

</style>