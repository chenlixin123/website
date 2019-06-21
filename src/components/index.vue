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
              <a href="javascript:void(0)" @click="goAnchor('#anchor-'+5)" :class="msg == '#anchor-5' ? 'a2' : 'a1'">有偿信息<div :class="msg == '#anchor-5' ? 'h1' : 'h2'"></div></a>
              <!-- <a href="javascript:void(0)" @click="goAnchor('#anchor-'+6)" :class="msg == '#anchor-6' ? 'a2' : 'a1'">联系我们<div :class="msg == '#anchor-6' ? 'h1' : 'h2'"></div></a> -->
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
            <!-- 1 -->
            <div class="news" @click="pay">
                <div class="left">
                    <div>08</div>
                    <div>2019/05</div>
                </div>
                <div class="right">
                    <div>2019年中国智慧停车行业市场分析</div>
                    <div>2019年5月7日以“智慧停车.城市更从容”为主题、打造“互联网+智慧停车”融合发展、构建……</div>
                </div>
                <div class="button" @click="pay">1元/条</div>
            </div>
            <!-- 2 -->
            <div class="news" @click="pay">
                <div class="left">
                    <div>13</div>
                    <div>2019/04</div>
                </div>
                <div class="right">
                    <div>2018年中国智慧停车市场投资现状及趋势分析</div>
                    <div>停车作为智慧交通中重要的一环，有着高频、刚需的特性，但始终面临机动车……</div>
                </div>
                <div class="button" @click="pay">1元/条</div>
            </div>
            <!-- 3 -->
             <div class="news" @click="pay">
                <div class="left">
                    <div>02</div>
                    <div>2019/04</div>
                </div>
                <div class="right">
                    <div>2019年中国机械停车设备行业市场分析</div>
                    <div>以“创新、突破、协作、共赢”为主题的2019中国城市停车大会暨中国停车设备行业……</div>
                </div>
                <div class="button" @click="pay">1元/条</div>
            </div>
             <!-- 4 -->
            <div class="news"  @click="pay">
                <div class="left">
                    <div>26</div>
                    <div>2019/03</div>
                </div>
                <div class="right">
                    <div>智能停车时代已到来，停车难不再难</div>
                    <div>2019年3月24日，城市地下空间开发及利用高峰论坛暨老猫智泊项目品鉴会在杭州……</div>
                </div>
                <div class="button" @click="pay">1元/条</div>
            </div>
             <!-- 5 -->
             <div class="news" @click="pay">
                <div class="left">
                    <div>26</div>
                    <div>2019/03</div>
                </div>
                <div class="right">
                    <div>2018年智慧停车市场分析：走向全视频化</div>
                    <div>按照信息化的程度，全球智慧停车行业发展可以分为三个阶段……</div>
                </div>
                <div class="button" @click="pay">1元/条</div>
            </div>
            <!-- 6 -->
            <div class="news" @click="pay">
                <div class="left">
                    <div>20</div>
                    <div>2019/03</div>
                </div>
                <div class="right">
                    <div>2019智慧停车行业趋势，百亿级市场渐具雏形</div>
                    <div>随着国民经济快速增长，汽车保有量节节攀升。据悉，2018年全国新注册登……</div>
                </div>
                <div class="button" @click="pay">1元/条</div>
            </div>
            <!-- 7 -->
             <div class="news" @click="pay">
                <div class="left">
                    <div>18</div>
                    <div>2019/02</div>
                </div>
                <div class="right">
                    <div>2018年中国独角兽企业成长趋势解读</div>
                    <div>随着中国经济增长与城市化进程不断加快，城市人口与小汽车数量迅猛增加，交通拥堵难……</div>
                </div>
                <div class="button" @click="pay">1元/条</div>
            </div>
              <!-- 8 -->
            <div class="news" @click="pay">
                <div class="left">
                    <div>09</div>
                    <div>2019/01</div>
                </div>
                <div class="right">
                    <div>停车APP为何在隐私与便捷之间如此难做抉择？</div>
                    <div>“你说这停车APP应用，我是删了呢还是删了呢?” 随着自助停车应用渐渐普及……</div>
                </div>
                <div class="button" @click="pay">1元/条</div>
            </div>
              <!-- 9 -->
            <div class="news" @click="pay">
                <div class="left">
                    <div>19</div>
                    <div>2018/12</div>
                </div>
                <div class="right">
                    <div>2018年智慧停车行业发展概况与2019年趋势分析</div>
                    <div>随着国民经济快速增长，居民消费水平日益增高，汽车不再是昂贵的消费品，在国内已实……</div>
                </div>
                <div class="button" @click="pay">1元/条</div>
            </div>
             <!-- 10 -->
             <div class="news" @click="pay">
                <div class="left">
                    <div>14</div>
                    <div>2018/12</div>
                </div>
                <div class="right">
                    <div>智慧停车行业现状及未来</div>
                    <div>我国汽车保有量持续增加，随之停车需求也进一步上升，“停车难”的情况逐渐成为智……</div>
                </div>
                <div class="button" @click="pay">1元/条</div>
            </div>
              <!-- 11 -->
             <div class="news" @click="pay">
                <div class="left">
                    <div>20</div>
                    <div>2018/11</div>
                </div>
                <div class="right">
                    <div>出行却怕停车难？MyPark的折叠机器人能自动帮你“占车位”</div>
                    <div>“停车难”是大城市生活的老大难题，但在停车场转来转去寻找停车位的日子……</div>
                </div>
                <div class="button" @click="pay">1元/条</div>
            </div>
            <!-- 12 -->
            <div class="news" @click="pay">
                <div class="left">
                    <div>13</div>
                    <div>2018/11</div>
                </div>
                <div class="right">
                    <div>共享汽车行业生存空间尚大，因地制宜规模化发展</div>
                    <div>近日，德国豪华汽车制造商戴姆勒和宝马在一定条件下合并汽车共享业务。戴姆勒和宝马……</div>
                </div>
                <div class="button" @click="pay">1元/条</div>
            </div>
             <!-- 13 -->
             <div class="news" @click="pay">
                <div class="left">
                    <div>06</div>
                    <div>2018/11</div>
                </div>
                <div class="right">
                    <div>德勤：数字技术可大大改善停车体验</div>
                    <div>对许多司机来说，停车是一种不可避免的高摩擦体验，无论是绕着街区转一圈，寻找一个……</div>
                </div>
                <div class="button" @click="pay">1元/条</div>
            </div>
             <!-- 14 -->
             <div class="news" @click="pay">
                <div class="left">
                    <div>20</div>
                    <div>2018/10</div>
                </div>
                <div class="right">
                    <div>智慧停车发展趋势分析 智能化技术推动可持续发展</div>
                    <div>智慧停车是破解停车难的最佳手段。智慧停车是利用物联网、移动支付等技术，优化停车……</div>
                </div>
                <div class="button" @click="pay">1元/条</div>
            </div>
             <!-- 15 -->
            <div class="news" @click="pay">
                <div class="left">
                    <div>04</div>
                    <div>2018/10</div>
                </div>
                <div class="right">
                    <div>2018年智慧停车的5个趋势</div>
                    <div>智慧停车，属于静态交通，按照停车地点，又可以分为路内停车、路外停车两种。智慧停车利……</div>
                </div>
                <div class="button" @click="pay">1元/条</div>
            </div>
        </div>
        <div class="bottoms">
            <div class="name">
              <div>客服专线：400 6090 210（周一至周五9:30-18:30）</div>
              <div @click="record">
                   <div>北京凌猫智行科技发展有限公司</div> 
                   <div>京ICP备19005685号</div>  
              </div>
            </div>
            <div class="number">
              <div>商务合作：business@linkmoretech.cn</div>
              <div>北京市朝阳区朝阳北路103号12层</div>
            </div>
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
 },
 //跳转备案查询网站
 record(){
    window.location.href = 'http://www.beian.miit.gov.cn'
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
          // border: 1px solid;
      width: 72%;
      height: 100%;
      margin: 0 auto;
      display: flex;
      justify-content: flex-end;
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
        margin-left: 25px;
        div{
          margin-left: 5px;
          color: black;
          cursor:pointer;
        }
      }
      img{
        // margin-top: 4px;
        // margin-right: 100px;
        position: absolute;
        top: 13px;
        left: 11%;
        width: 12%;
        // height: 26px;
      }
      .a1{
        font-size: 7px;
        color: #999;
        text-decoration:none;
        height: 12px;
        margin-top: 17px;
        border-bottom: 1.1px solid white;
        margin-left: 25px;
      }
        .a2{
        font-size: 7px;
        color: #333;
        text-decoration:none;
         height: 15px;
         margin-top: 19px;
          font-weight: bold;
          margin-left: 25px;
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
         margin-left: 25px;
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
        margin-left: 25px;
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
          width:14%;
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
          width:21%;
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
      // height: 400%;
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
              color: #f66913;
            }
            :nth-child(2){
              width: 380px;
              text-align: left;
              font-size: 6px;
              color: #666;
              // border: 1px solid;
            }
            // :nth-child(2):hover{
            //   color: #f66913;
            // }
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
    .bottoms{
      width: 100%;
      height: 40px;
      border: 1px solid;
      background: #333;
      color: #fff;
      font-size: 6px;
      box-sizing: border-box;
      // padding-left: 5%;
      .name{
        // border: 1px solid white;
        width: 55%;
        height: 35%;
        margin: 0 auto;
        margin-top: 9px;
        display: flex;
        justify-content: space-between;
        :nth-child(2){
          display: flex;
          cursor:pointer;
          :nth-child(2){
            margin-left: 7px;
          }
        }
      }
      .number{
         width: 55%;
        // height: 15%;
        margin: 0 auto;
        display: flex;
        justify-content: space-between;
        // margin-top: 10px;
        :nth-child(2){
          margin-right: 14%;
        }
      }
    }
    }
    }
</style>
