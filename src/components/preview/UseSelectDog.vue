<template>
  <div>
    <Dog
      v-for="(obj, index) in arr"
      :key="index"
      :imgurl="obj.dogImgUrl"
      :dogname="obj.dogName"
      @love="fn"
    ></Dog>

    <hr />
    <p>显示喜欢的狗:</p>
    <ul>
      <li v-for="(item, index) in loveArr" :key="index">{{ item }}</li>
    </ul>
  </div>
</template>

<script>
import Dog from "@/components/three/SelectDog.vue";
export default {
  data() {
    return {
      // 1. 准备数据
      arr: [
        {
          dogImgUrl:
            "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fi0.hdslb.com%2Fbfs%2Farticle%2F7612865c9cf94dfc85eb175ca9613d3acc106fc8.jpg&refer=http%3A%2F%2Fi0.hdslb.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1666541348&t=d1a0b867ce52758a959b0be67dc4934e",
          dogName: "蕾姆①号😌",
        },
        {
          dogImgUrl:
            "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fi0.hdslb.com%2Fbfs%2Farticle%2Ff92fea39f8d186e6cc695b7dcaaf764c3b6ed015.jpg&refer=http%3A%2F%2Fi0.hdslb.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1666541379&t=60a560eaa525d3a26266c7a18a61d88d",
          dogName: "蕾姆②号❤",
        },
        {
          dogImgUrl:
            "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fbos.nj.bpc.baidu.com%2Fv1%2Fmediaspot%2F497f45f604c2a05facc7c4fd005a1ce2.jpg&refer=http%3A%2F%2Fbos.nj.bpc.baidu.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1666541418&t=f28ea83dff764ee94490b44aed3a714a",
          dogName: "蕾姆③号😙",
        },
        {
          dogImgUrl:
            "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fi0.hdslb.com%2Fbfs%2Farticle%2F3c49f7e962e4eb36ebec40b06b454fa19fa01dfe.jpg&refer=http%3A%2F%2Fi0.hdslb.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1666541472&t=6afd86987f62ba40ade440ed4c017b2a",
          dogName: "蕾姆④号😍",
        },
        {
          dogImgUrl:
            "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fi0.hdslb.com%2Fbfs%2Farticle%2F6091da41c9ea3913ba9892f8f6e51a6b3c00c258.jpg&refer=http%3A%2F%2Fi0.hdslb.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1666541498&t=3ffb5dd7dd357d5c4a57fa52a63742db",
          dogName: "蕾姆⑤号😊",
        },
        {
          dogImgUrl:
            "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fnimg.ws.126.net%2F%3Furl%3Dhttp%3A%2F%2Fdingyue.ws.126.net%2F2021%2F0403%2F125de344j00qqyv0805vtc003g9064wm.jpg%26thumbnail%3D650x2147483647%26quality%3D80%26type%3Djpg&refer=http%3A%2F%2Fnimg.ws.126.net&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1666541532&t=b02ad2100721bcda22da230ebcaacc6c",
          dogName: "蕾姆⑥号(づ￣ 3￣)づ",
        },
      ],
      loveArr: []
    };
  },
  components: {
    Dog,
  },
  methods: {
    fn(dogName) {
      this.loveArr.push(dogName)
    },
  },
};
</script>

<style >
</style>