<template><v-app-bar>

  <template v-slot:prepend>
    <div class="module-search-box__wrapper">
      <ModuleSearchBox />  
    </div>
  </template>

  <v-spacer></v-spacer>

  <template v-slot:append>
      <v-btn v-for="btn in btnGroup"><span>{{btn.text}}</span></v-btn>
      <v-btn variant="flat" color="red-accent-2" class="ml-4 px-8 py-2">
        <span class="text-white font-weight-bold">登录</span>
      </v-btn>
  </template>  
</v-app-bar></template>
<script setup>
	import { ref, watch } from 'vue'
  import ModuleSearchBox from "./ModuleSearchBox"

  const btnGroup = {
    about: {text: "关于抖音"},
    download: {text: "下载抖音"},
    originatorSever: {text: "创作者服务"},
    postVideo: {text: "发布视频"}
  };
</script>
<style lang="sass">
  .module-search-box__wrapper
  .btn-group__wrapper
</style>
