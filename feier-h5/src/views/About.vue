<template>
  <div class="about">
    <p>全选：</p>
    <input type="checkbox" id="checkbox" v-model="checked" @click="changeAllChecked()" />
    <label for="checkbox">{{checked}}</label>
    <p>多个复选框：</p>
    <input type="checkbox" id="runoob" value="Runoob" v-model="checkedNames" />
    <label for="runoob">Runoob</label>
    <input type="checkbox" id="google" value="Google" v-model="checkedNames" />
    <label for="google">Google</label>
    <input type="checkbox" id="taobao" value="Taobao" v-model="checkedNames" />
    <label for="taobao">taobao</label>
    <br />
    <span>选择的值为:{{checkedNames}}</span>
  </div>
</template>
<script>
export default {
  data() {
    return {
      checked: false,
      checkedNames: [],
      checkedArr: ["Runoob", "Taobao", "Google"]
    };
  },
  methods: {
    changeAllChecked: function() {
      if (this.checked) {
        this.checkedNames = this.checkedArr;
      } else {
        this.checkedNames = [];
      }
    }
  },
  watch: {
    checkedNames: function() {
      if (this.checkedNames.length == this.checkedArr.length) {
        this.checked = true;
      } else {
        this.checked = false;
      }
    }
  }
};
</script>

