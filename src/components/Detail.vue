<template>
    <div>
        <header class="navbar  ">
            <div class="nav-wrap-left" @click="goto">
                <a class="back" href="#" onclick="javascript: window.history.back(); return false"><i class="icon-back"></i></a>
            </div>
            <h1 class="nav-header">猫眼电影</h1>
          </header>

        <div class="search-header">
          <div class="input-wrapper">
            <img class="search-icon" src="//s0.meituan.net/bs/?f=my-canary:/deploy/images/search.png" alt="">
            <input class="search-input" type="text" placeholder="搜影院">
            <img class="del-input" style="display:none" src="//s0.meituan.net/bs/?f=my-canary:/deploy/images/close.png" alt="">
          </div>
          <div class="cancel" onclick="javascript: window.history.back();">取消</div>
        </div>
    </div>
</template>
<script type="text/javascript">
    
    import '../styles/all.css'
    
    export default {
        methods:{
            goto(){
                console.log(this)
                this.$router.push({path:'/app/ciname'})
            }
        }
    }


</script>

<style scoped >
    
.navbar {
    height: 50.5px;
    color: #fff;
    background: #e54847;
    border-bottom: 1px solid #e54847;
    display: -webkit-box;
    display: -ms-flexbox;
    position: relative;
    font-family: Helvetica Neue,Helvetica,Arial,sans-serif;
}
.navbar .nav-wrap-left {
    height: 50.5px;
    width: 50.5px;
    line-height: 50.5px;padding: 0 15px;
}
.nav-wrap-left .icon-backback {
    height: 50px;
    width: 22.5px;
    line-height: 50px;
    
}
.icon-back {
    display: inline-block;
    width: 22.5px;
    height: 22.5px;
    vertical-align: middle;
    position: relative;
}
.icon-back:before {
    content: "";
    display: block;
    position: absolute;
    top: 0;
    width: 16px;
    height: 16px;
    border-bottom: 2px solid #fff;
    border-left: 2px solid #fff;
    -webkit-transform: rotate(45deg);
    transform: rotate(45deg);
}
.nav-header {
    display: block;
    -webkit-box-flex: 1;
    -ms-flex: 1;
    font-size: 18px;
    font-weight: 400;
    text-align: center;
    line-height: 50px;
    margin: 0 52.5px 0 0;
    text-overflow: ellipsis;
    white-space: nowrap;
    overflow: hidden;
}
</style>