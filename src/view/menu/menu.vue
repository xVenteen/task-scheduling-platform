<template>
    <div class="menu">
        <el-menu :collapse="datas.unfold" active-text-color="rgb(64, 158, 255)" background-color="#222d32"
            class="el-menu" default-active="1" text-color="rgb(191, 203, 217)" @open="handleOpen" @close="handleClose">
            <el-menu-item class="title" index="1" style="background: #00284d;">
                <div class="img"><img src="@/assets/logo.png" alt=""></div>
                <span class="text">任务调度平台</span>
            </el-menu-item>
            <el-menu-item index="2">
                <el-icon>
                    <span class="iconfont icon-baobiao"></span>
                </el-icon>
                <span>运行报表</span>
            </el-menu-item>
            <el-menu-item index="3">
                <el-icon>
                    <span class="iconfont icon-renwuqianyue"></span>
                </el-icon>
                <span>任务管理</span>
            </el-menu-item>
            <el-sub-menu index="4">
                <template #title>
                    <el-icon>
                        <span class="iconfont icon-a-wenjianjia-zhankai"></span>
                    </el-icon>
                    <span>日志管理</span>
                </template>
                <el-menu-item-group>
                    <el-menu-item index="4-1">调度日志</el-menu-item>
                    <el-menu-item index="4-2">操作日志</el-menu-item>
                </el-menu-item-group>
            </el-sub-menu>
            <el-menu-item index="5">
                <el-icon>
                    <span class="iconfont icon-iconfontzhizuobiaozhun0247"></span>
                </el-icon>
                <span>执行器管理</span>
            </el-menu-item>
            <el-sub-menu index="6">
                <template #title>
                    <el-icon>
                        <span class="iconfont icon-xitongguanli"></span>
                    </el-icon>
                    <span>系统管理</span>
                </template>
                <el-menu-item-group>
                    <el-menu-item index="6-1">用户管理</el-menu-item>
                    <el-menu-item index="6-2">角色管理</el-menu-item>
                    <el-menu-item index="6-3">系统配置</el-menu-item>
                    <el-menu-item index="6-4">快速选择</el-menu-item>
                </el-menu-item-group>
            </el-sub-menu>
        </el-menu>

    </div>

</template>

<script setup>
// import { setting } from "element-plus"
import '@/assets/style/iconfont.css'
// import { AddLocation } from '@element-plus/icons-vue'
import { ref, reactive, onMounted } from 'vue';
import emitter from '@/utils/mitt.js'
onMounted(() => {
    emitter.on('unfold', (msg) => {
        datas.unfold = msg.unfold
    })
});

const datas = reactive({
    unfold: false
})

</script>

<style lang='scss' scoped>
.menu {
    box-sizing: border-box;
    height: 100%;

    // .el-menu-vertical-demo:not(.el-menu--collapse) {
    //     width: 200px;
    //     min-height: 400px;
    // }

    .el-menu {
        height: 100%;
        border: 0;

        .title {
            font-size: 18px;
            font-weight: 600;
            color: rgb(225, 225, 225);

            img {
                width: 1.65vw;
                height: 1.65vw;
                vertical-align: middle;
                margin-right: 12px;
            }
        }

        .el-menu-item {
            width: 100%;
        }

        .el-sub-menu .el-menu-item {
            height: var(--el-menu-sub-item-height);
            line-height: var(--el-menu-sub-item-height);
            min-width: 0px;
        }
    }
}
</style>