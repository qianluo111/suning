<template>
  <a-layout id="components-layout-demo-side" style="min-height: 100vh">
    <a-layout-sider v-model="collapsed" collapsible>
      <div class="logo" />
      <a-menu 
            theme="dark"  
            mode="inline"
            v-model="optionKey"
      >
        <a-sub-menu key="sub1">
          <span slot="title">
            <a-icon type="home" />
              <span>起始页</span>
          </span>
          <a-menu-item key="1">
            <router-link to="/">后台首页</router-link>
          </a-menu-item>
        </a-sub-menu>
        <a-sub-menu key="sub2">
          <span slot="title"><a-icon type="bar-chart" /><span>舆情报告</span></span>
          <a-menu-item key="2">
             <router-link to="/Report">全部舆情</router-link>
          </a-menu-item>
          <a-menu-item key="3">
            <router-link to="/">
            正面舆情
            </router-link>
          </a-menu-item>
          <a-menu-item key="4">
             <router-link to="/">
            负面舆情
            </router-link>
          </a-menu-item>
        </a-sub-menu>
        <a-sub-menu key="sub3">
          <span slot="title"><a-icon type="setting" /><span>舆情设置</span></span>
          <a-menu-item key="5">
            <router-link to="/keywords">
            舆情关键词设置
            </router-link>
          </a-menu-item>
          <a-menu-item key="6">
            <router-link to="/Alarm">
            舆情报警设置
            </router-link>
          </a-menu-item>
        </a-sub-menu>
        
      </a-menu>
    </a-layout-sider>
    <a-layout>
      <a-layout-header style="height:25px;background: #f0f2f5; padding: 0" />
      <a-layout-content style="margin: 16px 16px">
        
        <div :style="{ padding: '24px', background: '#fff', minHeight: '360px' }">
          <router-view></router-view>
        </div>
      </a-layout-content>
    </a-layout>
  </a-layout>
</template>
<script>

export default {
    name:'Admin',
    components:{
        
    },
  data() {
    return {
      collapsed: false,
      optionKey:['sub1','sub2','sub3']
    };
  },
};
</script>


<style>
#components-layout-demo-side .logo {
  height: 32px;
  background: rgba(255, 255, 255, 0.2);
  margin: 16px;
}
</style>
