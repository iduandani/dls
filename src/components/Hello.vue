<template>
  <div class="hello">
  
    <div class='hgz hgz1'>
  
    </div>
  
    <div class='hgz hgz2'>
      <div class="wdj wdj2">
        <img src="../assets/imgs/wdj.gif" />
        <span class="txt txtwdj2">温度计</span>
      </div>
    </div>
    <div class='hgz hgz3'>
  
    </div>
    <div class='hgz hgz4'>
         <span class="txt txtwd">温度</span>
    </div>
    <div class='hgz hgz5'>
       <span class="txt txtyw">液位</span>
    </div>
    <div class='hgz hgz6'>
      <div class="llj2 llj">
        <img src="../assets/imgs/ld.png" />
        <span class="txt txtllj2">流量计</span>
      </div>
  
    </div>
    <div class='hgz hgz7'>
       <span class="txt txtwd2">温度</span>
    </div>
    <div class='hgz hgz8'>
       <span class="txt txtyw2">液位</span>
        <div class="wdj wdj4">
          <img src="../assets/imgs/wdj.gif" />
          <span class="txt txtwdj4">温度计</span>
        </div>
    </div>
  
    <div class='gz gz1'>
      <div class="llj1 llj">
        <img src="../assets/imgs/ld.png" />
         <span class="txt txtllj1">流量计</span>
      </div>
      <div class="wdj wdj1">
        <img src="../assets/imgs/wdj.gif" />
        <span class="txt txtwdj1">温度计</span>
      </div>
    </div>
  
    <div class='gz gz2'>
  
    </div>
  
    <div class='gz gz3'>
  
    </div>
    <div class='gz gz4'>
    
    </div>
    <div class='gz gz6'>
  
    </div>
    <div class='gz  gz7'>
  
    </div>
    <div class='gz gz5'>
  
    </div>
    <div class='gz gz9'>
  
    </div>
    <div class='gz gz8'>
      <div class="wdj wdj3">
        <img src="../assets/imgs/wdj.gif">
          <span class="txt txtwdj3">温度计</span>
      </div>
    </div>
    <div class='sx'>
      <img src="../assets/imgs/sx.gif" />
       <span class="txt txtsx1">瞬时功率</span>
    </div>
    <div class='sx2'>
       <span class="txt txtsx2">空气源热泵组</span>
      <img src="../assets/imgs/sx.gif" />
       <span class="txt txtsx3">瞬时功率</span>
    </div>
    <div class='tyndc'>
       <span class="txt txttyn">太阳能集热板</span>
      <img src="../assets/imgs/tyndc.gif" />
    </div>
    <div class='rsx'>
      <img src="../assets/imgs/rsx.gif" />
      <span class="txt txtrsx">热水箱</span>
    </div>
    <div class='rsx2'>
      <img src="../assets/imgs/rsx.gif" />
      <span class="txt txtrsx2">太阳能热水箱</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'hello',
  data() {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped >
img {
  width: 100%;
}

.hello {
  width: 1000px;
  height: 100%;
  background: #646464;
  margin: 0 auto;
  position: relative;
}

.sx {
  width: 200px;
  position: absolute;
  top: 60px;
  left: 0px;
}

.sx2 {
  width: 200px;
  position: absolute;
  top: 60px;
  left: 260px;
}

.tyndc {
  width: 260px;
  position: absolute;
  left: 660px;
  top: 80px;
}

.rsx {
  width: 180px;
  position: absolute;
  left: 8px;
  top: 470px;
}

.rsx2 {
  width: 180px;
  position: absolute;
  left: 270px;
  top: 470px;
}

.gz {
  background: url('../assets/imgs/gz1.gif') repeat-y;
  width: 20px;
  background-size: 100% auto;
  position: absolute;
  border-radius: 5px;
}

.gz1 {
  height: 210px;
  top: 240px;
  left: 10px;
}

.gz2 {

  height: 55px;
  top: 190px;
  left: 45px;
}

.gz3 {
  top: 190px;
  left: 70px;
  height: 95px;
}

.gz4 {
  height: 50px;
  top: 450px;
  left: 75px;
}

.gz5 {
  top: 280px;
  left: 280px;
  height: 270px;
}

.gz6 {
  top: 190px;
  left: 320px;
  height: 95px;
}

.gz7 {
  top: 200px;
  height: 250px;
  left: 380px;
}

.gz9 {
  height: 370px;
  top: 220px;
  left: 764px;
}

.gz8 {
  height: 290px;
  top: 257px;
  left: 510px;
}


.hgz {
  background: url('../assets/imgs/gz2.gif') repeat-x left center;
  height: 16px;
  position: absolute;
  background-size: auto 100%;
  border-radius: 5px;
}

.hgz1 {

  top: 235px;
  width: 35px;
  left: 20px;
}

.hgz2 {

  top: 275px;
  width: 250px;
  left: 80px;
}

.hgz3 {

  top: 440px;
  width: 370px;
  left: 20px;
}

.hgz4 {

  top: 540px;
  width: 190px;
  left: 100px;
}

.hgz5 {

  top: 580px;
  width: 220px;
  left: 100px;
}

.hgz6 {

  top: 252px;
  width: 250px;
  left: 520px;
}

.hgz7 {

  top: 540px;
  width: 120px;
  left: 400px;
}

.hgz8 {

  top: 580px;
  width: 375px;
  left: 400px;
}

.llj1 {
  position: absolute;
  top: 30px;
  width: 20px;
  height: 20px;
  background: #fff;
  text-align: center;
}

.llj2 {
  position: absolute;
  left: 60px;
  width: 20px;
  height: 20px;
  background: #fff;
  text-align: center;
}

.llj img {
  width: 160%;
  margin: -30%
}

.wdj img {
  width: 160%;
  margin: -40% 0 0 -45%;
}

.wdj1 {
  position: absolute;
  top: 130px;
  width: 20px;
  height: 20px;
  background: #fff;
  text-align: center;
}

.wdj2 {
  position: absolute;
  left: 40px;
  width: 20px;
  height: 20px;
  background: #fff;
  text-align: center;
}

.wdj3 {
  position: absolute;
  top: 100px;
  width: 20px;
  height: 20px;
  background: #fff;
  text-align: center;
}
.wdj4{
 position: absolute;
  left: 140px;
  width: 20px;
  height: 20px;
  background: #fff;
  text-align: center;
}
.txt{
  position: absolute;
  color: #fff;
  font-size: 12px;
}
.txtwdj1{
  left:-50px;
  width: 50px;
  text-align: center;
  top: 1px;
}
.txtwdj3{
  left:-50px;
  width: 50px;
  text-align: center;
  top: 1px;
}
.txtwdj2{
  left:-15px;
  width: 50px;
  text-align: center;
  bottom:-20px;
}
.txtwdj4{
  left:-15px;
  width: 50px;
  text-align: center;
  bottom:-20px;
}
.txtllj1{
  left:-50px;
  width: 50px;
  text-align: center;
  top: 1px;
}
.txtllj2{
 left:-15px;
  width: 50px;
  text-align: center;
  bottom:-20px;
}
.txtsx1{
  width: 13px;
  top: 50px;
  left: -10px;
}
.txtsx3{
  width: 13px;
  top: 50px;
  right: -10px;
}
.txtsx2{
  width: 13px;
  top: 30px;
  left: -35px;
}
.txttyn{
  font-size: 14px;
  width: 130px;
  top: 15px;
  left: 105px;
}
.txtrsx{
  font-size: 14px;
  width: 130px;
  bottom: 25px;
  right:-105px;
}
.txtrsx2{
  font-size: 14px;
  width: 130px;
  bottom: 25px;
  right:-105px;
}
.txtwd{
  left: -80px;
  top: -12px;
}
.txtyw{
  left: -80px;
  top: -12px;
}
.txtwd2{
  left: -107px;
  top: -12px;
}
.txtyw2{
  left: -107px;
  top: -12px;
}
h1,
h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
