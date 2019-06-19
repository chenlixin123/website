<template>
    <div class="box">
        <div class="title">
            <img src="@/assets/img/logo@3x.png" alt="">
            <div class="tap" @click="back">
                <img src="@/assets/img/fanhui@3x.png" alt="">
                <div>首页</div>
            </div>
        </div>
        <div class="center">
            <div class="img">
                 <img src="@/assets/img/beijing@2x.png" alt="" width="100%" height="100%">
            </div>
            <div class="centers">
                    <img src="@/assets/img/baibeijing@3x.png" alt="">
                    <div class="text" v-if="loginShow == true">
                        <input class="user" type="number" @input="phone" oninput="if(value.length>11)value=value.slice(0,11)" :value="phones"  placeholder="请输入手机号">
                        <img class="user_icon" src="@/assets/img/zhanghao@3x.png" alt="">
                        <input class="password" :value="passwords" type="password" @input="password" placeholder="请输入密码">
                        <img class="password_icon" src="@/assets/img/mima@3x.png" alt="">
                        <div class="logon" @click="logon">免费注册></div>
                        <button @click="taps">登录</button>
                    </div>
                    <div class="text" v-else>
                        <input  type="number" :value="phones" @input="phone"  oninput="if(value.length>11)value=value.slice(0,11)"  placeholder="请输入手机号" >
                        <input  type="password" :value="passwords" @input="password" placeholder="请输入密码">
                        <input  type="password" :value="confirm_passwords" @input="confirm_password" placeholder="请确认密码">
                        <button @click="tap">注册</button>
                    </div>
            </div>
        </div>
        <div class="module" v-if="show == true">
          <div class="err">
            <div class="err_text">{{err_text}}</div>
            <div class="confirm" @click="cancel">确定</div>
          </div>
        </div>
    </div>
</template>

<script>
import axios from "@/lib/api.request";
import Cookies from "js-cookie";
import Url from "@/lib/url";
export default {
    data(){
        return{
            data:'',
            phones:'',
            passwords:'',
            passwords_length:'',
            confirm_passwords:'',
            err_text:'',
            show:false,
            loginShow:true,
        }
    },
    methods:{
        // 注册
        tap(){
            let that = this
             let mobile_verify = /^(((13[0-9]{1})|(15[0-9]{1})|(18[0-9]{1})|(17[0-9]{1})|(19[0-9]{1})|(16[0-9]{1}))+\d{8})$/;
            console.log('注册')
            if(that.phones == ''){
               that.show = true,
               that.err_text = '手机号不能为空'
            }else if(!mobile_verify.test(that.phones)){
                that.show = true,
                that.err_text = '请输入正确的手机号'
            }else if(that.passwords == ''){
                that.show = true,
                that.err_text = '密码不能为空'
            }else if(that.passwords_length < 6){
                 that.show = true,
                that.err_text = '密码不能少于6位'
            }else if(that.passwords_length > 8){
                that.show = true,
                that.err_text = '密码不能大于8位'
            }else if(that.confirm_passwords == ''){
                that.show = true,
                that.err_text = '确认密码不能为空'
            }else if(that.passwords != that.confirm_passwords){
                that.show = true,
                that.err_text = '输入密码不一致'
            }else{
                console.log(that.phones,that.passwords)
                axios.request({
                    method:'post',
                    url:Url.url.logon,
                    params:{
                        mobile:that.phones,
                        password :that.passwords
                    }
                }).then(res => {
                    if(res.status == false || res.data == false){
                         that.show = true,
                         that.err_text = res.message.content
                    }else{
                         that.show = true,
                         that.err_text = '注册成功'
                         that.loginShow = true,
                         that.phones = '',
                         that.passwords = '',
                         that.confirm_passwords = ''
                    }
                })
            }
        },
        // 登录
        taps(){
             let that = this
             let mobile_verify = /^(((13[0-9]{1})|(15[0-9]{1})|(18[0-9]{1})|(17[0-9]{1})|(19[0-9]{1})|(16[0-9]{1}))+\d{8})$/;
            if(that.phones == ''){
               that.show = true,
               that.err_text = '手机号不能为空'
            }else if(!mobile_verify.test(that.phones)){
                that.show = true,
                that.err_text = '请输入正确的手机号'
            }else if(that.passwords == ''){
                that.show = true,
                that.err_text = '密码不能为空'
            }else{
                  axios.request({
                    method:'post',
                    url:Url.url.login,
                    params:{
                        mobile:that.phones,
                        password :that.passwords
                    }
                }).then(res => {
                    console.log(res)
                    if(res.status == false){
                         that.show = true,
                         that.err_text = res.message.content
                    }else{
                        //  that.show = true,
                        //  that.err_text = '登录成功'
                         sessionStorage.setItem('phone',res.data)
                         that.phones = '',
                         that.passwords = '',
                         that.$router.push({
                             path:'/'
                         })
                    }
                })
            }
            
        },
        // 切换登录
        logon(){
            let that = this
            that.loginShow = false
            that.phones = ''
            that.passwords = ''
            console.log('切换注册')
        },
        // 点击首页
        back(){
            let that = this
            that.$router.push({
                path:'/'
            })
        },
        // 输入手机号
        phone(e){
            let that = this
            that.phones = e.target.value
            console.log(e.target.value)
        },
        // 输入密码
        password(e){
            let that = this
            that.passwords = e.target.value
            that.passwords_length = e.target.value.length
             console.log(e.target.value.length)
        },
        // 确认密码
        confirm_password(e){
            let that = this
            that.confirm_passwords = e.target.value
             console.log(e.target.value)
        },
        // 取消弹出框
        cancel(){
            let that = this
            that.show = false
        }
    }
}
</script>

<style lang="scss" scoped>
    .box{
        width: 100%;
        height: 87.2%;
        // box-sizing: border-box;
        // padding-top: 56px;
        .title{
            width: 100%;
            height: 45px;
            margin: 0 auto;
            display: flex;
            box-sizing: border-box;
            padding: 0 10%;
            justify-content: space-between;
            align-items: center;
            // position:fixed;
            // top: 0;
            // left: 0;
            background: white;
            img{
                width: 17%;
            }
            .tap{
                width: 5%;
                display: flex;
                justify-content: space-around;
                align-items: center;
                // border: 1px solid;
                img{
                    width: 4px;
                    height: 6px;
                }
                div{
                    font-size: 8px;
                    cursor:pointer
                }
            }
        }
        .center{
            width: 100%;
            height: 100%;
            // background:url('../assets/img/beijing@3x.png') no-repeat;
            box-sizing: border-box;
            padding-top: 40px;
            position: relative;
            .img{
                width: 100%;
                height: 100%;
                position: absolute;
                top: 0;
                left: 0;
            }
            .centers{
            width: 70%;
            height: 250px;
            margin: 0 auto;
            position: relative;
            img{
                width: 100%;
                height: 100%;
            }
            .text{
                width: 35%;
                height: 55%;
                position:absolute;
                top: 27%;
                right: 8%;
                // border: 1px solid red;
                input{
                    width: 80%;
                    height: 30px;
                    border: none;
                    outline: none;
                    border-bottom: 1px solid #999;
                    background: white;
                    position: relative;
                }
                .user{
                    box-sizing: border-box;
                    padding-left: 15px;
                }
                .password{
                    box-sizing: border-box;
                    padding-left: 15px;
                }
                .user_icon{
                    position: absolute;
                    width: 9px;
                    height: 9px;
                    left: 0;
                    top: 9px;;
                }
                .password_icon{
                     position: absolute;
                    width: 9px;
                    height: 9px;
                    left: 0;
                    top: 40px;;
                }
                .logon{
                    width: 20%;
                    text-align: right;
                    color: #f66913;
                    font-size: 6px;
                    margin-left: 60%;
                    margin-top: 10px;
                    // border: 1px solid;
                    cursor:pointer;
                }
                button{
                    width: 80%;
                    height: 20px;
                    margin-top: 30px;
                    border-radius: 16px;
                    outline: none;
                    border: none;
                    background: #f66913;
                    color: white;
                    cursor:pointer;
                }
            }
            }
        }
        .module{
            width: 100%;
            height: 100%;
            position: fixed;
            top: 0;
            left: 0;
            background: rgba(0, 0, 0, 0.5);
            .err{
            width: 25%;
            height: 17%;
            position: absolute;
            top: 50%;
            left: 38%;
            background: white;
            box-sizing: border-box;
            padding: 1% 0;
            border-radius: 8px;
            .err_text{
                width: 100%;
                height: 40%;
                text-align: center;
                line-height: 15px;
                border-bottom: 1px solid #999;
                padding: 1.5% 0;
            }
            .confirm{
                 width: 100%;
               height: 50%;
                text-align: center;
                line-height: 30px;
                cursor:pointer;
                font-size:10px;
                // border: 1px solid;
            }
        }
        }
    }
</style>


