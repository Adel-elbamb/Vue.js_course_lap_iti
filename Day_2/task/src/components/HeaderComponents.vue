<template>
  <div class="bg-info d-flex justify-content-center">
    <h1 class="text-light ">Welcome {{ data.name }} , Branch:{{ data.branch }},track:{{ data.track }}</h1>
  </div>
</template>

<script >
export default {
    name:"HeaderComponents" ,
    data :()=>({}) ,
    props:["data"]
};
</script>

<style>

</style>