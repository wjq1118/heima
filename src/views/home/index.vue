<template>
<!-- 先定义一个大容器 -->
    <el-container>
        <!-- 先放置一个左侧 -->
        <el-aside style="width:200px">
            <layout-aside></layout-aside>
        </el-aside>
        <!-- 右侧 -->
        <el-container>
            <el-header>
                <layout-header></layout-header>
            </el-header>
            <!-- 中部区域 -->
            <el-main>
                <!-- 二级路由容器 -->
                <router-view></router-view>
            </el-main>
        </el-container>
    </el-container>
</template>
<script>

export default {

}
</script>

<style lang="">

</style>
