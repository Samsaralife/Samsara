<template>
    <div id="bottom_nav">
        <div id="middle">
            <div id="center">
            </div>
            <div id="line-1">
                <div id="left">
                    Property in copyright  IBM(Beijing)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
                    <span>Address:Beijing HaiDian District &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Postal Code:10000</span>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

export default {
  name: 'Foot'
}
</script>

<style>
#bottom_nav {
  float: left;
  position: relative;
  width: 100%;
  min-width: 320px;
  height: 110px;
  margin: 0px auto;
  margin-top: 1px;
  margin-right: auto;
  margin-bottom: 0px;
  margin-left: auto;
  background: #184481;
  z-index: 10;
  margin-top: 300px;
}
#middle {
    width: 1100px;
    height: 110px;
    padding: 0px;
    padding-top: 0px;
    padding-bottom: 0px;
    margin: 0px auto;
    position: relative;
    overflow: hidden;
}
#center {
    position: absolute;
    left: 50%;
    top: 50%;
    margin-left: 60px;
    margin-top: 48px;
}
#line-1 {
    float: left;
    position: relative;
    margin: 0 auto;
    width: 1100px;
    height: 40px;
    line-height: 40px;
}
#left {
    float: center;
    height: 40px;
    font-size: 15px;
    color: #fff;
    margin-top: 30x;
}
</style>
