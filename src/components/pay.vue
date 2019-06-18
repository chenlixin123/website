<template>
    <div class="body">
        <div class="title">
            <img src="@/assets/img/shouyintai@3x.png" alt="">
            <div class="text">收银台</div>
        </div>
        <div class="center">
            <div class="company">
                <div class="company_name">北京凌猫智行科技发展有限公司</div>
                <div class="many">
                    <div class="number">1</div>
                    <div class="text">元/条</div>
                </div>
            </div>
            <div class="bank">
                <div class="bank_title">
                    <div class="left">
                        <img src="@/assets/img/yinhangka@3x.png" alt="">
                        <div class="text">银行卡支付</div>
                    </div>
                    <div class="right"></div>
                </div>
                <div class="bank_center">
                    <div class="phone">
                        <input type="number" @input="phone"  oninput="if(value.length>11)value=value.slice(0,11)" placeholder="输入预留手机号即可快捷充值">
                        <button @click="confirm">确定</button>
                    </div>
                    <div class="banks">
                        <img @click="img" src="@/assets/img/zaixianzhifu@3x.png" alt="">
                        <img @click="img" src="@/assets/img/gongshang@3x.png" alt="">
                        <img @click="img" src="@/assets/img/nonghang@3x.png" alt="">
                        <img @click="img" src="@/assets/img/zhongguoyinhang@3x.png" alt="">
                        <img @click="img" src="@/assets/img/jianhang@3x.png" alt="">
                        <img @click="img" src="@/assets/img/zhaohang@3x.png" alt="">
                        <img @click="img" src="@/assets/img/jiaohang@3x.png" alt="">
                        <img @click="img" src="@/assets/img/zhongxin@3x.png" alt="">
                    </div>
                </div>
            </div>
            <div class="bottom">
            <div class="bottom_title">常见问题</div>
            <!-- 1 -->
            <div class="text_title">1、银行卡支付需不需要开通网上银行?</div>
            <div class="text">答：快捷支付不需要开通网上银行，网银支付需要开通网上银行。</div>
            <!-- 2 -->
            <div class="text_title">2、银行卡支付支持哪些类型的卡?</div>
            <div class="text">答：借记卡、信用卡。</div>
            <!-- 3 -->
            <div class="text_title">3、如何修改预留手机号码?</div>
            <div class="text">答：请确认您是否在银行已经预留手机号码，如未预留或已遗忘，请携带身份证及银行卡至银行网点柜台，告知银行工作人员修改成您的常用手机号码。</div>
            <!-- 4 -->
             <div class="text_title">4、可以使用他人借记卡开通快捷支付么?</div>
            <div class="text">答：不可以。为了您的支付账号和银行借记卡的安全，请使用本人银行卡开通快捷支付。</div>
            <!-- 5 -->
             <div class="text_title">5、各家银行的支付限制额度相同吗?</div>
            <div class="text">答：不同的银行开放的支付额度不同，每家银行根据不同的用卡条件(短信验证码、Ukey)设定不同的支付额度。如需了解各家银行具体的额度，可通过点击银行图标进行查看。</div>
            <!-- 6 -->
             <div class="text_title">6、造成“支付被拒绝”的原因有哪些?</div>
            <div class="text">答：(1)所持银行卡尚未开通网上在线支付功能;</div>
            <div class="text">(2)所持银行卡已过期、作废、挂失;</div>
            <div class="text">(3)所持银行卡内余额不足;</div>
            <div class="text">(4)输入银行卡卡号或密码不符;</div>
            <div class="text">(5)输入证件号不符;</div>
            <div class="text">(6)银行系统数据传输出现异常;</div>
            <div class="text">(7)网络中断;</div>
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
export default {
    data(){
        return{
            data:'',
            mobile:'',
            show:false,
            err_text:'',
        }
    },
    methods:{
        // 输入预留手机号
        phone(e){
            let that = this
            that.mobile = e.target.value
            console.log(e.target.value)
        },
        // 确定
        confirm(){
            let that = this
             let mobile_verify = /^(((13[0-9]{1})|(15[0-9]{1})|(18[0-9]{1})|(17[0-9]{1})|(19[0-9]{1})|(16[0-9]{1}))+\d{8})$/;
            if(that.mobile == ''){
               that.show = true,
               that.err_text = '手机号不能为空'
            }else if(!mobile_verify.test(that.mobile)){
                that.show = true,
                that.err_text = '请输入正确的手机号'
            }else{
                 window.location.href = 'https://www.baidu.com/'
            }
        },
        img(){
                 window.location.href = 'https://www.baidu.com/'
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

    .body{
        width: 100%;
        height: 100%;
        .title{
            width: 100%;
            height: 54px;
            display: flex;
            justify-content: flex-start;
            align-items: center;
            box-sizing: border-box;
            padding: 0 15%;
            img{
                width: 8%;
            }
            div{
                font-size: 13px;
                color: #666;
                margin-left: 12px;
            }
        }
        .center{
            width: 100%;
            // height: 100%;
            background: #f5f5f5;
            box-sizing: border-box;
            padding: 20px 0;
            .company{
                width: 70%;
                height: 54px;
                margin: 0 auto;
                display: flex;
                justify-content: space-between;
                align-items: center;
                .company_name{
                    width: 70%;
                    height: 54px;
                    text-align: center;
                    line-height: 54px;
                    background: #fdf7f4;
                    border: 1px solid #d6d5d5;
                    font-size: 13px;
                    font-weight: 540;
                }
                .many{
                     width: 30%;
                    height: 54px;
                    display: flex;
                    justify-content: center;
                    align-items: center;
                    background: #f8e1d4;
                    border: 1px solid #d6d5d5;
                    cursor: pointer;
                    .number{
                        font-size:23px;
                        color: #f66913;
                        font-size: bold;
                    }
                    .text{
                        font-size: 13px;
                        color: #666;
                    }
                }
            }
            .bank{
                width: 70%;
                height: 200px;
                margin: 0 auto;
                margin-top: 30px;
                border-top: 1.1px solid #cacaca;
                .bank_title{
                    width: 100%;
                    height: 50px;
                    display: flex;
                    .left{
                        width: 25%;
                        height: 100%;
                        background: white;
                        display: flex;
                        justify-content: center;
                        align-items: center;
                        img{
                            width: 25%;
                            height: 40%;
                            margin-right: 5px;
                        }
                        .text{
                            font-size: 10px;
                            color: #333;
                        }
                    }
                    .right{
                        width: 75%;
                        height: 100%;
                        border-left: 1px solid #cacaca;
                        border-bottom: 1px solid #cacaca;
                    }
                }
                .bank_center{
                    width: 100%;
                    height: 80%;
                    background: white;
                    box-sizing: border-box;
                    padding: 20px 50px;
                    .phone{
                        width: 100%;
                        height: 20px;
                        // border: 1px solid red;
                        input::-webkit-input-placeholder {
                        /* placeholder颜色  */
                        color: #bebdbd;
                        /* placeholder字体大小  */
                        font-size: 7px;
                            }
                        input{
                            width: 40%;
                            height: 90%;
                            margin: 0;
                            padding: 0;
                            padding-left: 10px;
                            border: 1px solid #d9d7d7;
                            border-radius: 3px;
                            outline: none;
                        }
                        button{
                            width: 12%;
                            height: 95%;
                            outline: none;
                            border-radius: 3px;
                            border: 1px solid #d9d7d7;
                            color: white;
                            margin-left: 10px;
                            cursor: pointer;
                        }
                    }
                    .banks{
                        width: 100%;
                        height: 60%;
                        // border: 1px solid;
                        margin-top: 20px;
                        display: flex;
                        justify-content: space-between;
                        align-items: center;
                        flex-wrap: wrap;
                        img{
                            width: 24%;
                            height: 40%;
                            margin-left: 1px;
                            cursor: pointer;
                            // border: 1px solid red;
                        }
                        // img:hover{
                               
                        //     }
                    }
                }
            }
             .bottom{
            width: 70%;
            margin: 0 auto;
            margin-top: 20px;
           box-sizing: border-box;
           padding: 21px 21px;
           background: #f8e1d4;
           border: 1px solid #f87e34;
           .bottom_title{
               font-size: 9px;
               color: #f66913;
               margin-bottom: 10px;
           }
           .text_title{
               font-size: 7px;
               color: #666;
               margin-bottom: 3px;
           }
           .text{
               font-size: 6px;
               color: #999;
               margin-bottom: 6px;
               line-height: 8px;
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
            height: 19%;
            position: absolute;
            top: 50%;
            left: 38%;
            background: white;
            box-sizing: border-box;
            padding: 1% 0;
            border-radius: 8px;
            .err_text{
                width: 100%;
                height: 30px;
                text-align: center;
                line-height: 30px;
                border-bottom: 1px solid #999;
            }
            .confirm{
                 width: 100%;
                height: 30px;
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


