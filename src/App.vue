<template>
    <div>

      <!-- <BuyBook /> -->
      <!-- <SelectYouOrMe /> -->
      <!-- <NavBar /> -->
      <!-- <StuManage /> -->

      <!-- <UseDog /> -->
      <!-- <UseSellDog /> -->
      <!-- <UseSelectDog /> -->
      <ShopCar />
    </div>
</template>

<script>
import BuyBook from './components/two/BuyBook.vue'
import SelectYouOrMe from './components/two/SelectYouOrMe.vue'
import NavBar from './components/two/NavBar.vue'
import StuManage from './components/two/StuManage.vue'
import UseDog from './components/preview/UseDog.vue'
import UseSellDog from './components/preview/UseSellDog.vue'
import UseSelectDog from './components/preview/UseSelectDog.vue'
import ShopCar from './components/three/ShopCar.vue'
export default {
  components: {
    BuyBook,
    SelectYouOrMe,
    NavBar,
    StuManage,
    UseDog,
    UseSellDog,
    UseSelectDog,
    ShopCar
  }
}
</script>

<style>

</style>