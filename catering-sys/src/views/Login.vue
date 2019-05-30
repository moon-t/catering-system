<template>
    <el-form :model="ruleForm" :rules="rules" ref="ruleForm" class="demo-ruleForm">
        <h3>登录</h3>
        <el-form-item props="account">
            <el-input v-model="ruleForm.account" autocomplete="off"
                placeholder="请输入账号"></el-input>
        </el-form-item>
        <el-form-item props="password">
            <el-input type="password" v-model="ruleForm.password" autocomplete="off"
                 placeholder="请输入密码"></el-input>
        </el-form-item>
        <el-form-item>
            <el-button type="primary" @click="loginToSys('ruleForm')">登录</el-button>
        </el-form-item>
    </el-form>
</template>

<style>
    .el-form{
        background-color: #f7f7f7;
        position: absolute;
        top: 50%;
        left: 50%;
        margin: -196px;
        width: 248px;
        height: 248px;
        padding: 36px;       
    }
    .el-button{
        width: 100%;
    }
</style>

<script>
import { login } from '../api/api'; 
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
                    var loginParams = {
                        username: this.ruleForm.account,
                        password: this.ruleForm.password,
                    };
                    login(loginParams).then(data => {
                        let { code, msg, user } = data;
                        if (code === 200){
                            sessionStorage.setItem('user',JSON.stringify(user));
                            this.$router.push({ path:'/home'})
                        }else{
                            Notification.error({
                                message:msg
                            });
                        }
                    })
                }else{
                    console.log("error")
                    return false;
                }
            });
        },
    }
}
</script>
