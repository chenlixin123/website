<template>
  <div class="box">
        <div  class="title">
            <div class="title_link">
              <img src="@/assets/img/logo@3x.png" alt="">
              <a href="#" :class="msg == '#anchor-0' ? 'a3' : 'a1'" @click="tap">首页</a>
              <a href="javascript:void(0)" @click="goAnchor('#anchor-'+1)" :class="msg == '#anchor-1' ? 'a2' : 'a1'">产品服务<div :class="msg == '#anchor-1' ? 'h1' : 'h2'"></div></a>
              <a href="javascript:void(0)" @click="goAnchor('#anchor-'+2)" :class="msg == '#anchor-2' ? 'a2' : 'a1'">解决方案<div :class="msg == '#anchor-2' ? 'h1' : 'h2'"></div></a>
              <a href="javascript:void(0)" @click="goAnchor('#anchor-'+3)" :class="msg == '#anchor-3' ? 'a2' : 'a1'">loT技术<div :class="msg == '#anchor-3' ? 'h1' : 'h2'"></div></a>
              <a href="javascript:void(0)" @click="goAnchor('#anchor-'+4)" :class="msg == '#anchor-4' ? 'a2' : 'a1'">服务价值<div :class="msg == '#anchor-4' ? 'h1' : 'h2'"></div></a>
              <a href="javascript:void(0)" @click="goAnchor('#anchor-'+5)" :class="msg == '#anchor-5' ? 'a2' : 'a1'">新闻动态<div :class="msg == '#anchor-5' ? 'h1' : 'h2'"></div></a>
              <a href="javascript:void(0)" @click="goAnchor('#anchor-'+6)" :class="msg == '#anchor-6' ? 'a2' : 'a1'">联系我们<div :class="msg == '#anchor-6' ? 'h1' : 'h2'"></div></a>
              <button @click="login" v-if="user == null">登录</button>
              <div class="user" v-else>{{user}}<div @click="user_back">退出</div></div>
            </div>
        </div>
        <div>
        </div>

    <div class="contentview">
        <!-- 首图 -->
       <div class="shou">
        <img src="@/assets/img/banner@3x.png" alt="" class="img">
      </div>
      <!-- 第一部分 -->
          <div class="content1" :id="'anchor-'+1">
              <img class="img" src="@/assets/img/01@3x.png" alt="">
              <div class="img_all">
                <div>
                  <img src="@/assets/img/PRODUCT@3x.png" alt="">
                  <div>PRODUCT</div>
                  <div>移动应用（2C&2B）</div>
                  <div>车位loT设备+车位SaaS平台</div>
                </div>

                 <div>
                  <img src="@/assets/img/STRATEGY@3x.png" alt="">
                  <div>STRATEGY</div>
                  <div>聚焦商办领域头部车位资源</div>
                  <div>提供确定性车位服务</div>
                </div>

                 <div>
                   <img src="@/assets/img/VISION@3x.png" alt="">
                  <div>VISION</div>
                  <div>为传统停车资产管理运营赋能</div>
                  <div>提升效率&体验</div>
                </div>
              </div>
          </div>
          <!-- 第二部分 -->
        <div class="content2"  :id="'anchor-'+2">
            <img src="@/assets/img/02@3x.png" alt="" class="img">
            <img src="@/assets/img/jiejuefangan@3x.png" alt="" class="img1">
        </div>
      <!-- 第三部分 -->
        <div class="content3"  :id="'anchor-'+3">
            <img src="@/assets/img/03@3x.png" alt="" class="img">
            <img src="@/assets/img/IoTjishujiagou@3x.png" alt="" class="img1">
        </div>
        <!-- 第四部分 -->
        <div class="content4" :id="'anchor-'+4">
              <img class="img" src="@/assets/img/04@3x.png" alt="">
              <div class="img_all">
                <div>
                  <img src="@/assets/img/jiangbenzengxiao@3x.png" alt="">
                  <div>降本增效</div>
                  <div>科技化手段管理运营</div>
                  <div>盘活闲置车位创造供给</div>
                  <div>停车导流、潮汐车位</div>
                </div>

                 <div>
                  <img src="@/assets/img/zichanguanli@3x.png" alt="">
                  <div>资产管理</div>
                  <div>实时掌握车位资产运营数据</div>
                  <div>为车位资产评估提供支持</div>
                  <div>为楼宇生态运营提供数据支持</div>
                </div>

                 <div>
                   <img src="@/assets/img/tiyantisheng@3x.png" alt="">
                  <div>体验提升</div>
                  <div>消除停车的不确定性环节</div>
                  <div>提供差异化服务满足不同需求</div>
                  <div>防止占位、有序停车</div>
                </div>
              </div>
        </div>
        <!-- 第五部分 -->
         <div class="content5"  :id="'anchor-'+5">
            <img src="@/assets/img/05@3x.png" alt="" class="img">
            <div class="news"  @click="pay">
                <div class="left">
                    <div>22</div>
                    <div>2019/05</div>
                </div>
                <div class="right">
                    <div>长租车位授权功能全面上线</div>
                    <div>明天有位重要的客户要来拜访，但是停车场的车位特别紧张，好担心......</div>
                </div>
                <div class="button" @click="pay">1元/条</div>
            </div>
             <div class="news" @click="pay">
                <div class="left">
                    <div>21</div>
                    <div>2019/05</div>
                </div>
                <div class="right">
                    <div>凌猫受邀参加知行哓政WORK&WOW！办公体验节</div>
                    <div>5月24（周五），凌猫受邀请参加由知行哓政主办的聚焦办公体验的......</div>
                </div>
                <div class="button" @click="pay">1元/条</div>
            </div>
             <div class="news" @click="pay">
                <div class="left">
                    <div>25</div>
                    <div>2019/01</div>
                </div>
                <div class="right">
                    <div>凌猫停车APP上线新版本，新增实景选位功能</div>
                    <div>凌猫停车APP将于1月25日晚间上架新版本。在新版本中，有功能的新增，也有原功能的优化，下面跟着我来了解......</div>
                </div>
                <div class="button" @click="pay">1元/条</div>
            </div>
            <div class="news" @click="pay">
                <div class="left">
                    <div>11</div>
                    <div>2019/01</div>
                </div>
                <div class="right">
                    <div>凌猫科技再获行业认可，牵手仲量联行打造智慧物管</div>
                    <div>2019年1月9日，由中国房地产业协会指导，商办互联携手知行 哓政联合主办的.......</div>
                </div>
                <div class="button" @click="pay">1元/条</div>
            </div>
            <div class="news" @click="pay">
                <div class="left">
                    <div>28</div>
                    <div>2018/07</div>
                </div>
                <div class="right">
                    <div>@所有人，解锁新玩法，凌猫停车小程序上线了！</div>
                    <div>在这个激情的七月，凌猫迎来了自己的大事--小程序[凌猫停车]终于上线了......</div>
                </div>
                <div class="button" @click="pay">1元/条</div>
            </div>
        </div>
        <!-- 第六部分 -->
          <div class="content6"  :id="'anchor-'+6">
            <img src="@/assets/img/06@3x.png" alt="" class="img">
            <div class="top">
               <div class="top_left">
                  <div class="text">客服专线</div>
                  <div class="mobile">400-6090-210</div>
                  <div class="date">9:30-18:30 (周一至周五)</div>
               </div>
               <div class="top_right">  
                  <img src="@/assets/img/app@3x.png" alt="">
                  <div>下载APP</div>
               </div>
            </div>
            <div class="bottom">
               <div class="bottom_left">
                  <div class="text">合作邮箱</div>
                  <div class="mobile">business@linkmoretech.cn</div>
                  <div class="date">我们将会尽快给予您回复或咨询建议</div>
               </div>
               <div class="bottom_right">  
                   <img src="@/assets/img/xiaochengxu@3x.png" alt="">
                   <div>小程序</div>
               </div>
            </div>
        </div>
        <div class="bottoms">
            <div class="name">
              <div>北京凌猫智行科技发展有限公司</div>
              <div>地址：北京市朝阳区朝阳北路103号12层</div>
            </div>
            <div class="number">京ICP备19005685号</div>
        </div>
    </div>
</div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: '#anchor-0',
      user:''
    }
  },
  created(){
    let that = this
    that.user = sessionStorage.getItem('phone')
  },
  methods:{
    // 锚链接
     goAnchor(selector) {
       let that = this
       that.msg = selector
       console.log(selector)
  var anchor = this.$el.querySelector(selector)
  document.body.scrollTop = anchor.offsetTop; // chrome
  document.documentElement.scrollTop = anchor.offsetTop; // firefox
 },
//  退出
 user_back(){
   sessionStorage.removeItem('phone')
    let that = this
    that.user = sessionStorage.getItem('phone')
 },
//  点击首页
 tap(){
   this.msg = '#anchor-0'
 },
//  点击登录
 login(){
   let that = this
  //  sessionStorage.setItem('phone','15503062257')
   that.$router.push({
     path:'/login'
   })
 },
//  支付
 pay(){
    let that = this
    if(that.user == null){
       that.$router.push({
     path:'/login'
   })
    }else{
      that.$router.push({
     path:'/pay'
   })
    }
 }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    .box{
      width: 100%;
        box-sizing: border-box;
      padding-top: 40px;
      .title{
      width: 100%;
      height: 40px;
      position: fixed;
      top: 0;
      left: 0;
      background: white;
      z-index: 1000;
        .title_link{
      width: 80%;
      height: 100%;
      margin: 0 auto;
      display: flex;
      justify-content: space-around;
      align-items: center;
      a{
        position: relative;
        .h1{
          width: 13px;
          margin-top: 1.5px;
          margin-left: 25%;
          border-top: 1.1px solid #a7a7a7;
        }
        .h2{
          width: 13px;
          margin-top: 1.5px;
          margin-left: 25%;
          border-top: 1.1px solid white;
        }
      }
      .user{
        color: red;
        font-size: 8px;
        display: flex;
        margin-top: 12px;
        div{
          margin-left: 5px;
          color: black;
          cursor:pointer;
        }
      }
      img{
        width: 17%;
        height: 24px;
      }
      .a1{
        font-size: 7px;
        color: #999;
        text-decoration:none;
        height: 12px;
        margin-top: 17px;
        border-bottom: 1.1px solid white;
      }
        .a2{
        font-size: 7px;
        color: #333;
        text-decoration:none;
         height: 15px;
         margin-top: 19px;
          font-weight: bold;
        //  border-bottom: 1.1px solid #a7a7a7;
      }
      .a3{
         font-size: 7px;
        color: #333;
        text-decoration:none;
         height: 11px;
         border-bottom: 1.1px solid #a7a7a7;
         margin-top: 16px;
         font-weight: bold;
      }
      button{
        width: 35px;
        height: 15px;
        border: 1px solid #999;
        border-radius: 4px;
        text-align: center;
        line-height:15px;
        margin-top: 12px;
        font-size: 7px;
        color: #333;
        background: white;
        outline: none;
        cursor:pointer;
      }
    }
    }
    .img{
      width: 100%;
    }
    .contentview{
      .shou{
        .img{
          width: 100%;
        }
      }
      .content1{
      width: 100%;
      height: 280px;
      box-sizing: border-box;
      padding: 45px 10%;
      .img{
          width:13%;
      }
      .img_all{
        width: 80%;
        margin: 0 auto;
        margin-top: 30px;
        display: flex;
        justify-content: space-between;
        div{
          text-align: center;
          img{
            width: 40%;
        }
        :nth-child(2){
          font-size: 9px;
          color: #333;
          margin-top: 12px;
        }
        :nth-child(3){
          font-size: 7px;
          color: #666;
          margin-top: 10px;
        }
        :nth-child(4){
          font-size: 7px;
          color: #666;
          margin-top: 8px;
        }
        }
      }
      }
      .content2{
      width: 100%;
      height: 380px;
      box-sizing: border-box;
      padding: 45px 10%;
      text-align: center;
      background: #f5f5f5;
      .img{
          width:11%;
          display: block;
      }
      .img1{
         width: 50%;
         margin: 0 auto;
         margin-top: -20px;
      } 
    }
        .content3{
      width: 100%;
      height: 370px;
      box-sizing: border-box;
      padding: 45px 10%;
      .img{
          width:22%;
          margin-left:-23px;
      }
      .img1{
        width: 80%;
        // margin-top: 20px;
        margin-left: 10%;
      } 
    }
    // 第四部分
     .content4{
      width: 100%;
      height: 310px;
      box-sizing: border-box;
      padding: 45px 10%;
       background: #f5f5f5;
      .img{
          width:12%;
      }
      .img_all{
        width: 100%;
        margin: 0 auto;
        // margin-top: 30px;
        display: flex;
        justify-content: space-between;
        div{
          text-align: center;
          img{
            width: 50%;
        }
        :nth-child(2){
          font-size: 9px;
          color: #333;
          // margin-top: 12px;
        }
        :nth-child(3){
          font-size: 7px;
          color: #666;
          margin-top:7px;
        }
        :nth-child(4){
          font-size: 7px;
          color: #666;
          margin-top: 5px;
        }
         :nth-child(5){
          font-size: 7px;
          color: #666;
          margin-top: 5px;
        }
        }
      }
      }
      .content5{
      width: 100%;
      height: 480px;
      box-sizing: border-box;
      padding: 45px 10%;
      text-align: center;
      .img{
          width:11%;
          display: block;
      }
      .news{
        width: 87%;
        height: 65px;
        border-bottom: 1px  dashed #d4d4d4;
        margin-left: 10%;
        // margin-top: 30px;
        box-sizing: border-box;
        padding-top: 3%;
        display: flex;
        position: relative;
        cursor:pointer;
        .left{
            width: 8%;
            height: 35px;
            background: #f2f2f2;
            box-sizing: border-box;
            padding-top: 1%;
            color: #666;
            margin-right:20px;
            :nth-child(1){
              font-size: 9px;
            }
             :nth-child(2){
              font-size: 8px;
            }
        }
        .right{
            :nth-child(1){
              text-align: left;
              margin-top: 6px;
              margin-bottom: 7px;
              font-size: 8px;
              color: #333;
            }
            :nth-child(1):hover{
              color: red;
            }
            :nth-child(2){
              width: 380px;
              text-align: left;
              font-size: 6px;
              color: #666;
              // border: 1px solid;
            }
            :nth-child(2):hover{
              color: red;
            }
        }
        .button{
          width: 50px;
          height: 20px;
          text-align: center;
          line-height: 20px;
          border: 1px solid #c9c9c9;
          border-radius: 4px;
          font-size: 8px;
          color: #999;
          position: absolute;
          top: 25px;
          right: 10px;
          cursor:pointer;
        }
      }
    }
      .content6{
      width: 100%;
      height: 270px;
      box-sizing: border-box;
      padding: 30px 10%;
       background: #f5f5f5;
      .img{
          width:11%;
      }
      .top{
        width: 60%;
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin: 0 auto;
        margin-top: 10px;
        .top_left{
          // margin-left: 10%;
          height: 100%;
          .text{
              font-size: 10px;
              color: #333;
          }
          .mobile{
            margin-top: 5px;
            margin-bottom: 5px;
            font-size: 8px;
            color: #333;
          }
          .date{
            font-size: 6px;
            color: #666;
          }
        }
        .top_right{
          img{
            width: 50px;
            height: 50px;
          }
          div{
            text-align: center;
            font-size: 7px;
          }
        }
      }
      .bottom{
          width: 60%;
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin: 0 auto;
        margin-top: 20px;
        .bottom_left{
          // margin-left: 10%;
          height: 100%;
          .text{
              font-size: 10px;
              color: #333;
          }
          .mobile{
            margin-top: 5px;
            margin-bottom: 5px;
            font-size: 8px;
            color: #333;
          }
          .date{
            font-size: 6px;
            color: #666;
          }
        }
        .bottom_right{
          img{
            width: 50px;
            height: 50px;
          }
          div{
            text-align: center;
            font-size: 7px;
          }
        }
      }
    }
    .bottoms{
      width: 100%;
      height: 40px;
      border: 1px solid;
      background: #333;
      color: #fff;
      font-size: 6px;
      box-sizing: border-box;
      padding: 0px 10px;
      .name{
        width: 50%;
        height: 35%;
        margin: 0 auto;
        margin-top: 9px;
        display: flex;
        justify-content: space-between;
        :nth-child(2){
          margin-left: 40%;
        }
      }
      .number{
         width: 50%;
        // height: 15%;
        margin: 0 auto;
        display: flex;
        justify-content: flex-start;
        // margin-top: 10px;
      }
    }
    }
    }
</style>
