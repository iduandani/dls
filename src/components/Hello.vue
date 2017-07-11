<template>
  <div class="hello">
  
    <div class='hgz hgz1'>
  
    </div>
  
    <div class='hgz hgz2'>
      <div class="wdj wdj2">
        <img src="../assets/imgs/wdj.gif" />
        <span class="txt txtwdj2">{{thermomter1}}</span>
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
        <span class="txt txtllj2">{{flowmeter1}}</span>
      </div>
  
    </div>
    <div class='hgz hgz7'>
      <span class="txt txtwd2">温度</span>
    </div>
    <div class='hgz hgz8'>
      <span class="txt txtyw2">液位</span>
      <div class="wdj wdj4">
        <img src="../assets/imgs/wdj.gif" />
        <span class="txt txtwdj4">{{thermomter3}}</span>
      </div>
    </div>
  
    <div class='gz gz1'>
      <div class="llj1 llj">
        <img src="../assets/imgs/ld.png" />
        <span class="txt txtllj1">{{flowmeter}}</span>
      </div>
      <div class="wdj wdj1">
        <img src="../assets/imgs/wdj.gif" />
        <span class="txt txtwdj1">{{thermomter}}</span>
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
        <span class="txt txtwdj3">{{thermomter3}}</span>
      </div>
    </div>
  
    <div class='gj gj1'>
  
    </div>
    <div class='gj gj2'>
  
    </div>
    <div class='gj gj3 '>
  
    </div>
    <div class='gj gj4 gjbg2'>
  
    </div>
    <div class='gj gj5 gjbg2'>
  
    </div>
    <div class='gj gj6 gjbg2'>
  
    </div>
    <div class='gj gj7 gjbg2'>
  
    </div>
    <div class='gj gj8'>
  
    </div>
    <div class='gj gj9 gjbg2'>
  
    </div>
    <div class='gj gj10 gjbg2'>
  
    </div>
    <div class='sx'>
      <img src="../assets/imgs/sx.png" />
      <span class="txt txtsx1">瞬时功率</span>
    </div>
    <div class='sx2'>
      <span class="txt txtsx2">空气源热泵组</span>
      <img src="../assets/imgs/sx.png" />
      <span class="txt txtsx3">瞬时功率</span>
    </div>
    <div class='tyndc'>
      <span class="txt txttyn">太阳能集热板</span>
      <img src="../assets/imgs/tyndc.png" />
    </div>
    <div class='rsx'>
      <img src="../assets/imgs/rsx.png" />
      <span class="txt txtrsx">储热水箱</span>
    </div>
    <div class='rsx2'>
      <img src="../assets/imgs/rsx.png" />
      <span class="txt txtrsx2">太阳能热水箱</span>
    </div>
  </div>
</template>

<script>
import ajax from 'axios'
var TWEEN = require('@tweenjs/tween.js');
export default {
  name: 'hello',
  data() {
    return {
      "flowmeter": "0",   //流量1
      "flowmeter1": "0", //流量2
      "thermomter": "0",    //温度1
      "thermomter1": "0",  //温度2
      "thermomter2": "0",  //温度3
      "thermomter3": "0"  //温度4
    }
  },
  methods: {
    async startGetDate() {

      // while (true) {
      //   await this.wait(5 * 1000);
      this.getData();
      // }

    },
    async wait(time) {
      return new Promise(r => {
        setTimeout(() => {
          r();
        }, time)
      })

    },
    animate(name, oldv, newv) {
      var self = this;
      function _animate() {
        if (TWEEN.update()) {
          requestAnimationFrame(_animate)
        }
      }
      new TWEEN.Tween({ tweeningNumber: oldv })
        .easing(TWEEN.Easing.Quadratic.Out)
        .to({ tweeningNumber: newv }, 1000)
        .onUpdate(function () {
          self[name] = this.tweeningNumber.toFixed(0)
        })
        .onComplete(() => {
          //cancelAnimationFrame(animationFrame)
        })
        .start()
      _animate()
    },
    getData(flag) {
      ajax.get('/Index/getSystemRealJson', {}).then(res => {
        if (res.data.status == 'success') {
          this.animate('flowmeter', this.flowmeter, res.data.flowmeter);
          this.animate('flowmeter1', this.flowmeter1, res.data.flowmeter1);
          this.animate('thermomter', this.thermomter, res.data.thermomter);
          this.animate('thermomter1', this.thermomter1, res.data.thermomter1);
          this.animate('thermomter2', this.thermomter2, res.data.thermomter2);
          this.animate('thermomter3', this.thermomter3, res.data.thermomter3);
        } else {
          let msg = res.data.msg || '网络错误'
          alert(msg);
        }
      }).catch(e => {
        alert('网络错误');
      });
    }
  },
  mounted() {
    this.startGetDate();
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
  left: 20px;
}

.sx2 {
  width: 200px;
  position: absolute;
  top: 60px;
  left: 260px;
}

.tyndc {
  width: 290px;
  position: absolute;
  left: 660px;
  top: 90px;
}

.gj {
  width: 16px;
  height: 16px;
  background: url('../assets/imgs/gzgj.png');
  background-size: 100% 100%;
  position: absolute;
}

.gj.gjbg2 {
  background: url('../assets/imgs/gzgj2.png');
  background-size: 100% 100%;
}

.gj1 {
  left: 30px;
  top: 235px;
}

.gj2 {
  left: 30px;
  top: 444px;
  transform: rotate(0deg) rotateX(180deg)
}

.gj3 {
  left: 90px;
  top: 279px;
  transform: rotate(0deg) rotateX(180deg)
}

.gj4 {
  left: 278px;
  top: 539px;
}

.gj5 {
  left: 63px;
  top: 234px;
}

.gj6 {
  left: 318px;
  top: 274px;
}

.gj7 {
  left: 378px;
  top: 439px;
}

.gj8 {
  left: 510px;
  top: 252px;
}

.gj9 {
  left: 508px;
  top: 539px;
}

.gj10 {
  left: 762px;
  top: 579px;
}

.rsx {
  width: 140px;
  position: absolute;
  left: 28px;
  top: 470px;
}

.rsx2 {
  width: 140px;
  position: absolute;
  left: 300px;
  top: 470px;
}

.gz {
  background: url('../assets/imgs/gz.png') repeat-y;
  width: 16px;
  background-size: 100% auto;
  position: absolute;
  border-radius: 5px;
}

.gz1 {
  height: 198px;
  top: 250px;
  left: 30px;
}


.gz2 {

  height: 50px;
  top: 190px;
  left: 65px;
}

.gz3 {
  top: 190px;
  left: 90px;
  height: 93px;
}

.gz4 {
  height: 50px;
  top: 453px;
  left: 95px;
}

.gz5 {
  top: 287px;
  left: 280px;
  height: 260px;
}

.gz6 {
  top: 190px;
  left: 320px;
  height: 90px;
}

.gz7 {
  top: 200px;
  height: 248px;
  left: 380px;
}

.gz9 {
  height: 370px;
  top: 220px;
  left: 764px;
}

.gz8 {
  height: 275px;
  top: 268px;
  left: 510px;
}


.hgz {
  background: url('../assets/imgs/hgz.png') repeat-x left center;
  height: 16px;
  position: absolute;
  background-size: auto 100%;
  border-radius: 5px;
}

.hgz1 {

  top: 235px;
  width: 30px;
  left: 40px;
}

.hgz2 {

  top: 275px;
  width: 226px;
  left: 100px;
}

.hgz3 {

  top: 440px;
  width: 345px;
  left: 40px;
}

.hgz4 {

  top: 540px;
  width: 185px;
  left: 100px;
}

.hgz5 {

  top: 580px;
  width: 240px;
  left: 100px;
}

.hgz6 {

  top: 252px;
  width: 250px;
  left: 520px;
}

.hgz7 {

  top: 540px;
  width: 115px;
  left: 400px;
}

.hgz8 {

  top: 580px;
  width: 370px;
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

.wdj4 {
  position: absolute;
  left: 140px;
  width: 20px;
  height: 20px;
  background: #fff;
  text-align: center;
}

.txt {
  position: absolute;
  color: #fff;
  font-size: 12px;
}

.txtwdj1 {
  left: -40px;
  width: 50px;
  text-align: center;
  top: 1px;
}

.txtwdj3 {
  left: -40px;
  width: 50px;
  text-align: center;
  top: 1px;
}

.txtwdj2 {
  left: -15px;
  width: 50px;
  text-align: center;
  bottom: -20px;
}

.txtwdj4 {
  left: -15px;
  width: 50px;
  text-align: center;
  bottom: -20px;
}

.txtllj1 {
  left: -40px;
  width: 50px;
  text-align: center;
  top: 1px;
}

.txtllj2 {
  left: -15px;
  width: 50px;
  text-align: center;
  bottom: -20px;
}

.txtsx1 {
  width: 13px;
  top: 50px;
  left: -10px;
}

.txtsx3 {
  width: 13px;
  top: 50px;
  right: -10px;
}

.txtsx2 {
  width: 13px;
  top: 30px;
  left: -25px;
}

.txttyn {
  font-size: 14px;
  width: 130px;
  top: -25px;
  left: 145px;
}

.txtrsx {
  font-size: 14px;
  width: 130px;
  bottom: 25px;
  right: -125px;
}

.txtrsx2 {
  font-size: 14px;
  width: 130px;
  bottom: 25px;
  right: -125px;
}

.txtwd {
  left: -80px;
  top: -12px;
}

.txtyw {
  left: -80px;
  top: -12px;
}

.txtwd2 {
  left: -100px;
  top: -12px;
}

.txtyw2 {
  left: -100px;
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
