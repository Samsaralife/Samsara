<template>
   <div id="top">
<div id="nav">
<ul>
    <li><a href="#">Home Page</a></li>
    <li><a href="#">Product</a>
    </li>
    <li><a href="#">Service</a>
    </li>
    <li><a href="#">Industry</a></li>
    <li><a href="#">Developer</a></li>
    <li><a href="#">Support</a></li>
    <li><a href="#">About Me</a>
        <ul>
            <li><a href="#">Product Feature</a></li>
            <li><a href="#">Product Center</a></li>
            <li><a href="#">Product Display</a></li>
            <li><a href="#">Contact  Us</a></li>
        </ul>
    </li>
    </ul>
</div>
</div>
</template>
<script>

export default {
  name: 'Header'
}
</script>

<style>
#top {
    width: 100%;
    min-width: 320px;
    position: relative;
    margin: 0 auto;
    margin-top: 0;
    margin-right: auto;
    margin-bottom: 0px;
    margin-left: auto;
    height: 80px;
    margin-top: 0;
    padding-top: 0;
    BACKGROUND-POSITION: top;
}
#nav {background: #184481;height:60px;line-height:60px;}
#nav li {list-style-type:none;float:left;font-size:20px;}
#nav li a {text-decoration:none;padding:0px 40px;color:#fff;
display:inline-block;}
#nav li a:hover {background:deepskyblue;}
#nav li ul {display:none;background:#184481;position: absolute;}
#nav li ul li {float: none;}
#nav li:hover ul {display:block;}
#nav li:hover ul li a:hover {background:deepskyblue;display:inline-block;}
</style>
