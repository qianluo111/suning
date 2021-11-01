<template>
  <div class="warp">
    <div class="denglu">
        <div class="title">舆情监控系统后台管理</div>
        <div class="form">
          <div class="user" >
            用户名:
            <input type="text" :username="username">
          </div>
          <div class="password" >
            密码:
            <input type="password" :password="password">
          </div>
          <div class="yanzheng">
            验证码:
            <input type="text" class="yan" :verify="verify">
            <span class="suiji" v-html="picture" :svgkeys="svgkeys"></span>
          </div>

          <div class="in">
          <router-link to="/">
            进入管理中心
          </router-link>
            </div>
        </div>
        <div class="img">
          <img src="../assets/zhizu.png"/>
        </div>
    </div>
  </div>
</template>
<script>
export default{
  name:'Login',
  data(){
    return{
        picture:{},
        imgId:0,
        username:"",
        password:"",
        verify:"",
        svgkeys:"",
    }
  },
  methods:{
    getsvgImgData(){
       let apis = 'http://yuqing.itying.com/api/captcha?svgImg='+this.svgImg+'&svgKey='+this.svgKey
        this.$axios.get(apis).then(({data})=>{
            // console.log(data)
            this.picture=data.svgImg;
            this.imgId=data.svgKey;
        });
    },
    getdengluData(){
      let doLogin= 'http://yuqing.itying.com/api/doLogin?username='+this.username+'&password='+this.password+'&verify='+this.verify+'&svgkey='+this.svgkeys
      this.$axios.post(doLogin).then(({data})=>{
            console.log(data)
            // this.picture=data.svgImg;
            // this.imgId=data.svgKey;
        });
    }
  },
  mounted(){
       this.getsvgImgData()
       this.getdengluData()
    },

}
</script>
<style lang="scss" scoped>
.warp{
  width: 100%;
  height: 100%;
  padding: 274px 0;
  background-color:rgb(1,69,142,);
  display:flex;
  flex-wrap:wrap ;
}
.denglu{
    width: 500px;
    height: 300px;
    margin: 0 auto;
    flex-wrap: wrap;
    display: flex;
    background:rgb(238, 239, 252);
  }
  .title{
    width: 100%;
    height: 20px;
    display: flex;
    font-size: 17px;
    padding: 0 5px;
   
    color: rgb(1,69,142,);
  }
  .form{
    width: 300px;
    height: 200px;
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    justify-content: space-around;
    background: yellow;
    margin: 0 20px;
  }
  .user{
    color: rgb(1,69,142,);
  }
  .password{
    color: rgb(1,69,142,);
    margin-left: 10px;
    // margin-right: 70px;
  }
  .yanzheng{
    width:100%;
    height: 50px;
    display: flex;
    justify-content: center;
    align-items: center;
    margin-right: 50px ;
    color: rgb(1,69,142,);
  }
  .yan{
      width: 60px;
      height: 20px;
      display: flex;
  }
  .suiji{
    width: 60px;
    height: 20px;
    margin-left: 20px;
    svg{
      width: 60px;
    height: 20px;
    }
  }
    .in{
      width: 100px;
      height: 20px;
      margin-top: 20px;
      color: white;
      background: rgb(230, 112, 22);
    }

    .img{
      width: 160px;
      height: 200px;
      background: black;
      img{
        width: 160px;
        height: 200px;
      }
    }

</style>
