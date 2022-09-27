<template>
  <div>
    <child-com :title="'姓名'">
      <input type="text" />
    </child-com>
    <child-com :title="'密码'">
      <input type="password" />
    </child-com>
    <child-com :title="'性别'">
      <input type="radio" name="sex" value="男" />男
      <input type="radio" name="sex" value="女" />女
    </child-com>
    <child-com :title="'爱好'">
      <input type="checkbox" value="抽烟" />抽烟
      <input type="checkbox" value="喝酒" />喝酒
      <input type="checkbox" value="烫头" />烫头
    </child-com>
    <child-com :title="'来自于'">
      <select>
        <option value="北京">北京</option>
        <option value="天津">天津</option>
        <option value="南京">南京</option>
      </select>
    </child-com>
  </div>
</template>

<script>
import MyCom from '../six/MyCom.vue'
export default {
    components: {
        ChildCom: MyCom
    }
};
</script>

<style>
</style>