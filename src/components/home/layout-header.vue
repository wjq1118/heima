<template>
  <!-- 我是最外层 -->
  <el-row class='layout-header' type="flex" justify="space-between">
    <!-- 左侧 -->
    <el-col :span="6">
      <i class="el-icon-s-unfold"></i>
      <span class="title">江苏传智播客教育科技股份有限公司</span>
    </el-col>
    <!-- 右侧 -->
    <el-col :span="4">
      <img class='head-img' src="../../assets/img/avatar.jpg" alt />
      <!-- 下拉菜单组件  el-dropdown -->
      <el-dropdown trigger="click">
          <!-- 匿名插槽 -->
        <span class="el-dropdown-link">
          下拉菜单
          <i class="el-icon-arrow-down el-icon--right"></i>
        </span>
            <el-dropdown-menu slot="dropdown">
        <el-dropdown-item icon="el-icon-user-solid">个人信息</el-dropdown-item>
        <el-dropdown-item icon="el-icon-house">git地址</el-dropdown-item>
        <el-dropdown-item icon="el-icon-refresh-right">退出</el-dropdown-item>
      </el-dropdown-menu>
      </el-dropdown>
    </el-col>
  </el-row>
</template>

<script>
export default {}
</script>

<style lang="less" scoped>
    .layout-header{
        height:50px;
        .el-icon-s-unfold{
            font-size: 22px;
        }
        .title{
            vertical-align: top;
            margin-left: 4px;
        }
        .head-img{
            width: 40px;
            height: 40px;
            border-radius: 50%;
            vertical-align: middle;
            margin-right: 4px;
        }
    }

</style>
