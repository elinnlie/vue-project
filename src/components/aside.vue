<template>
  <el-menu
    :style="{ width: !isCollapse ? '230px' : '64px' }"
    :default-active="active"
    class="aside-container"
    active-text-color="#67cebc" 
    background-color="#304156" 
    text-color="#bfcbd9"
    :collapse="isCollapse"
    @open="handleOpen"
    @close="handleClose"
  >
    <div class="logo-box">
      <el-icon v-if="isCollapse" :size="24"><Platform /></el-icon>
      <span v-else class="logo-text">康护云 SaaS</span>
    </div>
    <tree-menu :index="1" :menuData="menuData" />
  </el-menu>
</template>
<script setup>
import { reactive, computed } from "vue";
// import { useRouter } from 'vue-router'
import TreeMenu from "./treeMenu.vue";
import { useStore } from "vuex";

// const router = useRouter()
// const menuData = reactive(router.options.routes[0].children)
const menuData = computed(() => store.state.menu.routerList);
console.log(menuData, 'menuData')
const store = useStore();
const isCollapse = computed(() => store.state.menu.isCollapse);
const active = computed(() => store.state.menu.menuActive);
console.log(active);

const handleOpen = (key, keyPath) => {
  console.log(key, keyPath);
};
const handleClose = (key, keyPath) => {
  console.log(key, keyPath);
};
</script>

<style lang="less" scoped>
.aside-container {
  height: 100%;
  border-right: none; 
  transition: width 0.3s; 
  
  .logo-box {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 60px;
    line-height: 60px;
    color: #fff;
    background-color: #2b2f3a; 
    
    .logo-text {
      font-size: 18px;
      font-weight: bold;
      letter-spacing: 1px;
      white-space: nowrap;
    }
  }
}
</style>
