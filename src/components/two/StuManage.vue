<template>
  <div id="app">
    <div>
      <span>姓名:</span>
      <input type="text" v-model="user.uname"/>
    </div>
    <div>
      <span>年龄:</span>
      <input type="number" v-model="user.age"/>
    </div>
    <div>
      <span>性别:</span>
      <select v-model="user.gender">
        <option value="男">男</option>
        <option value="女">女</option>
      </select>
    </div>
    <div>
      <button @click="handle">添加/修改</button>
    </div>
    <div>
      <table
        border="1"
        cellpadding="10"
        cellspacing="0"
      >
        <tr>
          <th>序号</th>
          <th>姓名</th>
          <th>年龄</th>
          <th>性别</th>
          <th>操作</th>
        </tr>
        <tr v-for="(item, index) in list" :key="index">
          <td>{{ index }}</td>
          <td>{{ item.uname }}</td>
          <td>{{ item.age }}</td>
          <td>{{ item.gender }}</td>
          <td>
            <button @click="delFn(index)">删除</button>
            <button @click="editFn(index)">编辑</button>
          </td>
        </tr>
      </table>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
        list: [],
        editIndex: -1,
        user: {
            uname: '',
            age: '',
            gender: '男',
        }
    }
  },
  methods: {
    handle() {
        if (this.editIndex > -1) {
            this.$set(this.list, this.editIndex, { ...this.user })
            this.editIndex = -1
        } else {
            this.list.push({ ...this.user })
        }
        for (let k in this.user) {
            this.user[k] = ''
        }
        this.user.gender = '男'
    },
    delFn(index) {
        this.list.splice(index, 1)
    },
    editFn(index) {
        this.user = { ...this.list[index] }
        this.editIndex = index
    }
  }
}
</script>