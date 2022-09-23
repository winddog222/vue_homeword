<template>
  <div>
    <table
      border="1"
      width="700"
      style="border-collapse: collapse"
    >
      <caption>
        购物车
      </caption>
      <thead>
        <tr>
          <th>
            <input type="checkbox" v-model="isAll"/> <span>全选</span>
          </th>
          <th>名称</th>
          <th>价格</th>
          <th>数量</th>
          <th>总价</th>
          <th>操作</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(item, index) in goodList" :key="index">
            <td><input type="checkbox" v-model="item.checked"></td>
            <td>{{ item.name }}</td>
            <td>{{ item.price }}</td>
            <td>
                <button @click="item.num--" :disabled="item.num <= 1">-</button>
                <span class="item_num">{{ item.num }}</span>
                <button @click="item.num++">+</button></td>
            <td>{{ item.price * item.num }}</td>
            <td><button @click="goodList.splice(index, 1)">删除</button></td>
        </tr>
      </tbody>

      <tfoot v-if="goodList.length !== 0">
        <tr>
          <td>合计:</td>
          <td colspan="5">
            {{ allPrice }}
          </td>
        </tr>
      </tfoot>
    </table>
  </div>
</template>

<script>
export default {
  computed: {
    allPrice() {
        return this.goodList.reduce((sum, item) => item.checked ? item.price * item.num + sum : sum, 0)
    },
    isAll: {
        set(val) {
            this.goodList.forEach(item => item.checked = val)
        },
        get() {
            return this.goodList.every(item => item.checked)
        }
    }
  },
  data() {
    return {
      goodList: [
        {
          name: "诸葛亮",
          price: 1000,
          num: 1,
          checked: false,
        },
        {
          name: "蔡文姬",
          price: 1500,
          num: 1,
          checked: false,
        },
        {
          name: "妲己",
          price: 2000,
          num: 1,
          checked: false,
        },
        {
          name: "鲁班",
          price: 2200,
          num: 1,
          checked: false,
        },
      ],
    };
  },
};
</script>

<style>
tr {
    text-align: center;
}
.item_num{
    display: inline-block;
    width: 50px;
}
</style>