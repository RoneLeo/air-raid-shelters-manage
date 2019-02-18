<template>
  <el-row class="menu_page">
    <el-col>
      <el-menu
        class="el-menu-vertical-demo"
        background-color="#324057"
        text-color="#fff"
        active-text-color="#409eff"
      >
        <router-link to="/home">
          <el-menu-item index="0">
            <i class="fa fa-margin fa-server"></i>
            <span slot="title">首页</span>
          </el-menu-item>
        </router-link>
        <template v-for="item in items">
          <el-submenu v-if="item.children" :index="item.path" :key="item.path">
            <template slot="title">
              <i :class="'fa fa-margin '+item.icon"></i>
              <span slot="title">{{item.name}}</span>
            </template>
            <router-link v-for="(citem,cindex) in item.children" :to="citem.path" :key="cindex">
              <el-menu-item :index="citem.path">
                <span slot="title">{{citem.name}}</span>
              </el-menu-item>
            </router-link>
          </el-submenu>
        </template>
      </el-menu>
    </el-col>
  </el-row>
</template>

<script>
export default {
  name: "left-menu",
  data() {
    return {
      items: [
        {
          icon: "fa-asterisk",
          name: "人防工程规划管理",
          path: "fund",
          children: [{ path: "fundlist", name: "人防工程总体规划" },
          { path: "2", name: "人防工程详细规划" }]
        },
        {
          icon: "fa-asterisk",
          name: "人防工程审批管理",
          path: "info",
          children: [{ path: "3", name: "单建人防工程审批管理" },
          { path: "4", name: "结建人防工程审批管理" },
          { path: "5", name: "兼顾人防要求工程审批管理" },
          { path: "6", name: "防空地下室易地建设审批管理" },
          { path: "7", name: "人防工程竣工验收审批管理" },
          { path: "8", name: "人防工程拆除报废审批管理" },
          { path: "9", name: "人防工程资质审批管理" }]
        },
        {
          icon: "fa-asterisk",
          name: "质量监督与维护",
          path: "a",
          children: [{ path: "infoshow", name: "人防工程安全质量监督管理" },
          { path: "10", name: "人防工程改造维护建设管理" }]
        },
        {
          icon: "fa-asterisk",
          name: "平战结合管理",
          path: "b",
          children: [{ path: "11", name: "人防工程开发利用备案" },
          { path: "12", name: "人防工程平时使用证管理" },
          { path: "13", name: "人防工程平时使用安全管理" },
          ]
        },
        {
          icon: "fa-asterisk",
          name: "人防工程统计分析",
          path: "c",
          children: [{ path: "*", name: "人防工程信息管理" },
          { path: "/", name: "人防工程统计分析" },
          { path: "14", name: "人防工程专用图" },
          { path: "15", name: "人防工程地理信息管理" },]
        },
      ]
    };
  }
};
</script>


<style scoped>
.menu_page {
  position: fixed;
  top: 71px;
  left: 0;
  min-height: 100%;
  background-color: #324057;
  z-index: 99;
}
.el-menu {
  border: none;
}
.fa-margin {
  margin-right: 5px;
}
.el-menu-vertical-demo:not(.el-menu--collapse) {
  width: 240px;
  min-height: 400px;
}
.el-menu-vertical-demo {
  width: 35px;
}
.el-submenu .el-menu-item {
  min-width: 240px;
}

.hiddenDropdown,
.hiddenDropname {
  display: none;
}
a {
  text-decoration: none;
}
</style>
