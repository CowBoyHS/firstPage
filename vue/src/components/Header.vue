<template>
    <div style="height: 50px; line-height: 50px; border-bottom: 1px solid #ccc; display: flex">
        <div style="width: 200px; margin-left: 70px; font-weight: bold; color: dodgerblue">后台管理</div>
        <div style="flex: 1"></div>
        <div style="width: 100px; margin-top: 18px;">
            <el-dropdown style="align-items: center; ">
                <span class="el-dropdown-link">
                    {{user.username}}
                    <el-icon class="el-icon--right">
                        <arrow-down />
                    </el-icon>
                </span>
                <template #dropdown>
                    <el-dropdown-menu>
                        <el-dropdown-item>个人信息</el-dropdown-item>
                        <el-dropdown-item @click="$router.push('/login')">退出系统</el-dropdown-item>
                    </el-dropdown-menu>
                </template>
            </el-dropdown>
        </div>
    </div>
</template>

<script>

    export default {
        name: "Header",
        data() {
            return {
                user:{},
            }
        },
        created() {
            let userStr = sessionStorage.getItem("user") || "{}";
            this.user = JSON.parse(userStr);
        },
        components:{

        }
    }
</script>

<style scoped>

</style>