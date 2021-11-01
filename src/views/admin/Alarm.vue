<template>
  <div class="wrap">
    <div class="xinxi">
        <p class="text">
          <span>报警电话:</span>
        <input type="text" placeholder="180106qqq" />
        </p>
        <p class="text">
         <span>报警邮箱:</span>
        <input type="text" placeholder="1111111111@qq.commm11" />
        </p>
    </div>
    <button class="btn">保存</button>
  </div>
</template>
<script>
export default {
  name: "Alarm",
  components: {},
};
</script>


<style scoped>
.wrap {
  width: 100%;
  height: 700px;
  /* display: flex; */
  /* flex-wrap: wrap; */
  background: #fff;
}
/* p {
  width: 100%;
  height: 30px;
  display: flex;
  padding: 20px 20px;
  color: black;
  font-weight: bold;
} */
.xinxi{
    width: 100%;
    height: 70px;
    display: flex;
    flex-wrap: wrap;
}
.text{
    width: 100%;
    height: 30px;
    display: flex;
}
span{
  width: 65px;

}
input {
  width: 100%;
  height: 30px;
  outline: none;
  margin-left: 10px;
  border: 1px solid rgb(217, 217, 217);
  color: black;
}
.btn{
    width: 60px;
    height: 30px;
    background: rgb(24, 144, 255);
    float: right;
    margin-top: 20px;
    color: #fff;
    outline: none;
    border: none;
    letter-spacing: 3px;
}
</style>
