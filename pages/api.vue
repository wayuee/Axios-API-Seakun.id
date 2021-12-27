<template>
<div>
<CardApi :data-api="packets"> 
<template v-slot:bawah></template>  
</Cardapi>
</div>
</template>

<script>
import axios from "axios"
import CardApi from "~/components/mollecules/CardApi"
export default {
  components:{
    axios,
    CardApi
  },
  data(){
    return{
      packets:[]
    }
  },
  mounted(){
    this.getDataFromSeakun()
  },
  methods:{
    //GET= Ambil data , POST = Lempar data , PUT = edit data, DELETE = hapus data 
    //Disingkat jadi CRUD = Create , Read , Update , Delete
    getDataFromSeakun(){
      var api = "https://seakun-packet-api-v2.herokuapp.com/product-digital"
      axios .get(api)
            .then((res) => {
              this.packets = res.data
              console.log(this.packets);
            })
            .catch((err) => {
              console.log(err)
            })
    }
  }
}
</script>

<style>

</style>