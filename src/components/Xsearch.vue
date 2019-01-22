<template>
  <div class="white-bg topbar-bg ">
    <div class="city-entry">
      <span class="city-name">广州</span><i class="city-entry-arrow"></i>
    </div>
    
    <div class="switch-hot" data-active=".n-hot">
      <div class="hot-item " data-tab=".n-hot" v-for="item in list" :key="item.name"
       @click="isactive(item.name)"  :class="{active : active == item.name}" >{{item.name}}</div>
    </div>
    <div class="search-entry search-icon" data-type="movie"></div>
  </div>
</template>
<script>
    export default {
        data() {
            return {
                list:[
                    {name:'正在热播'},
                    {name:'即将上映'}
                ],
                active:'正在热播'
            };
        },
        methods: {
            isactive(name){
                this.active = name;
            
            }
        },
        //生命周期函数，请求数据
        created(){
            // axios.get()
        }
    }
</script>
<style scoped>
.topbar-bg {
    display: -webkit-box;
    display: flex;
    -webkit-box-align: center;
    align-items: center;
    height: 44px;
    -webkit-box-pack: justify;
    justify-content: space-between;
}

.search-input, .white-bg {
    background-color: #fff;
}
.city-entry {
    padding-left: 15px;
    font-size: 15px;
    color: #666;
    display: -webkit-box;
    display: flex;
    -webkit-box-align: center;
    align-items: center;
}
.switch-hot {
    display: -webkit-box;
    display: flex;
    height: 44px;
    line-height: 44px;
    position: relative;
}

.footerTab, a, div {
    -webkit-tap-highlight-color: transparent;
}
.search-icon {
    width: 20px;
    height: 20px;
    background: url(../assets/1.png) 10px no-repeat;
    background-size: 20px;
    padding: 10px 15px 10px 10px;
    color:#ef4238;
}

.footerTab, a, div {
    -webkit-tap-highlight-color: transparent;
}
.switch-hot .hot-item.active {
    color: #ef4238;
    border-bottom: 2px solid #ef4238;
}
.switch-hot .hot-item {
    font-size: 15px;
    color: #666;
    width: 80px;
    width: 21.33333vw;
    text-align: center;
    margin: 0 12px;
    font-weight: 700;
}

.footerTab, a, div {
    -webkit-tap-highlight-color: transparent;
}

</style>


