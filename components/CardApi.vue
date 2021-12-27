<template>

    <div class="w-full h-full grid xl:grid-cols-4 grid-cols-2 lg:grid-cols-3 gap-2 md:gap-4 lg:gap-6 xl:gap-6 px-0 justify-center pl-36 pr-40">
      <div class="w-full border-none max-w-sm bg-white shadow-xl rounded-xl overflow-hidden text-gray-900 md:pb-3 md:w-full md:h-full" style="height:580px; witdh:1000px;" v-for="(item,id) in dataApi " :key="id">
        <div class="md:h-48">
          <img class="w-full" :src="`/image/${item.slug}.png`" :alt="item.name">
        </div>
      <div class="w-full h-full relative px-2 py-0 flex-rows "> 
        <div class="h-full">
          <div class="flex pt-14 tn:pt-2 items-center mb-1 md:mb-2 md:px-2">
            <img class="w-8 ml-1" :src="`/icon/${item.slug}.svg`" alt="">
            <h5 class="md:text-base font-bold mx-2">{{item.name}}</h5>
          </div>
          <div class="tn:px-1 tn:py-1 md:px-2 md:mt-3 lg:px-4" v-for="(data,id) in item.packages" :key="id">
            <div class="text-xs md:text-sm md:flex md:justify-between mt-1">
              <p class="text-xl ">{{data.name}}</p>
              <p class="text-xl font-bold">Rp{{data.price}}<span class="text-xs font-light">/{{data.type}}</span></p>
            </div>
          </div>
          <p class="pl-5 pt-5 pb-20 text-xl font-semibold text-blue-400">Lihat scema harga</p>
          <div class="h-full absolute left-5 top-72 w-72 ">
            <hr class="pb-4 font-bold text-xl blue-700 ">
            <button class="w-full py-3 my-2 text-white text-xl font-bold border rounded-xl bg-blue-300">Pesan</button>
          </div> 
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props:{
    dataApi:{
      type:Array,
      default:[]
    }
  }
}
</script>

<style>
  *{
    box-sizing: border-box;
  }
</style>