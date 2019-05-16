<template>
    <el-form :model="ruleForm" :rules="rules" ref="ruleForm" class="demo-ruleForm">
        <h3>登录</h3>
        <el-form-item label="账号" props="account">
            <el-input v-model="ruleForm.account" autocomplete="off"></el-input>
        </el-form-item>
        <el-form-item label="密码" props="password">
            <el-input type="password" v-model="ruleForm.password" autocomplete="off"></el-input>
        </el-form-item>
        <el-form-item>
            <el-button type="primary" @click="loginToSys('ruleForm')">登录</el-button>
        </el-form-item>
    </el-form>
</template>
<script>
export default {
    data() {
        var validatePass = (rule, value, callback) => {
            if(value === ''){
                callback(new Error('请输入密码'));
            }else{
                callback();
            }
        };

        var validateAccount = (rule, value, callback) => {
            if(value === ''){
                callback(new Error('请输入账号'));
            }else{
                callback();
            }
        };

        return {
            ruleForm: {
                account:'',
                password:'',
            },
            rules: {
                account: [
                    { validator: validateAccount, tigger: 'blur'}
                ],
                password: [
                    { validator: validatePass, tigger: 'blur'}
                ],
            }
        };
    },
    methods: {
        loginToSys(formName) {
            this.$refs[formName].validate((valid) => {
                if (valid) {
                    alert("login")
                }else{
                    console.log("error")
                    return false;
                }
            });
        },
    }
}
</script>
