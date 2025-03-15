<template>
<div class="continar  row ">
 <!-- <div class="col-12"> <HeaderComponents name="ITI" branch="tanta" track="os"/></div>
  -->
 <div class="col-12"> <HeaderComponents :data="{name:'ITI', branch:'tanta' ,track:'os'}" /></div>


 <div class="col-12 h-100"><BodyComponents/></div>
 <div class="col-12"><FooterComponents/></div>
</div>
</template>

<script>
import HeaderComponents from './components/HeaderComponents.vue';
import FooterComponents from './components/FooterComponents.vue';
import BodyComponents from './components/BodyComponents.vue';
import ListComponents from './components/ListComponents.vue'

export default {
  name: 'App',
  components: {
    HeaderComponents,
    FooterComponents,
    BodyComponents, // Make sure this matches exactly
    ListComponents
  }
};
</script>

<style>
/* Add styles if needed */
</style>
