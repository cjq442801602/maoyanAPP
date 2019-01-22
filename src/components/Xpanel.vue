<template>
  <div class="tab-block">
    <div class="tab-content">
       <router-link :to="`/detail/${index}/${'app'}`"
        v-for="(n,index) in news"
        :key="index"
        >
      <div class="page active n-hot" data-hot=".n-hot" data-cid="c_dmLad">
        <div class="list-wrap" style="margin-top: 0px;">
          <div class="item" data-id="1206875" data-bid="dp_wx_home_movie_list">
            <div class="main-block">
              <div class="avatar" sort-flag>
                <div class="default-img-bg">
                  <img
                    :src="n.img|capitalize"
                    onerror="this.style.visibility='hidden'"
                  >
                </div>
              </div>
              <div class="mb-outline-b content-wrapper">
                <div class="column content">
                  <div class="box-flex movie-title">
                    <div class="title line-ellipsis v3dimax_title" v-text="n.nm"></div>

                    <span class="version v3d imax"></span>
                  </div>

                  <div class="detail column">
                    <div class="score line-ellipsis">
                      <span class="score-suffix" >观众评</span>
                      <span class="grade" v-text="n.sc"></span>
                    </div>

                    <div class="actor line-ellipsis" v-text="n.star"></div>

                    <div class="show-info line-ellipsis" v-text="n.showInfo"></div>
                  </div>
                </div>

                <div class="button-block" data-id="1206875">
                  <div class="btn normal">
                    <span class="fix" data-bid="dp_wx_home_movie_btn">购票</span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="more"></div>
      </div>
      <!-- <div class="page f-hot" data-hot=".f-hot" data-cid="c_3j5p10oz">
        <div class="list-wrap" style="margin-top: 0px;">
          <div class="most-expected">
            <div class="weui-loadmore">
            <i class="weui-loading"></i>
            <span class="weui-loadmore__tips">正在加载</span>
        </div>
            <div class="most-expected-list"></div>
          </div>
          <div class="coming-list"></div>
        </div>
        <div class="more"></div>
      </div> -->
       </router-link>
    </div>
    <div class="page f-hot" data-hot=".f-hot" data-cid="c_3j5p10oz">
        <div class="list-wrap" style="margin-top: 0px;">
          <div class="most-expected">
            <div class="weui-loadmore">
            <i class="weui-loading"></i>
            <span class="weui-loadmore__tips">正在加载</span>
        </div>
            <div class="most-expected-list"></div>
          </div>
          <div class="coming-list"></div>
        </div>
        <div class="more"></div>
      </div>
  </div>
  
</template>
<script src"../js/one.js"></script>
<script>

export default {
  // M
  data() {
    return {
      // 存放新闻数据
      news: []
    };
  },
  methods: {
    // 获取数据的方法
    async getNews() {
      let data = await this.$axios.get("http://localhost:3020");
      // let images=data.movieList.replace("w.h","128.180");
      // console.log(images)
      console.log(data.data.movieList);
      this.news = this.news.concat(data.data.movieList);
    }
  },
  //过滤器
  filters: {
  capitalize: function (value) {
     return value.replace(/w.h/g, "128.180")
  }
},
  created() {
    // 触发getNews方法
    
    this.getNews();
  }
};
</script>
<style scoped>
.tab-content .list-wrap {
    background-color: #f5f5f5;
}
.tab-content .list-wrap .item {
    padding-left: 15px;
    background-color: #fff;
}
.tab-content .list-wrap .item .main-block {
    position: relative;
    width: 100%;
}
.tab-content .list-wrap .item .avatar {
    width: 64px;
    height: 90px;
    position: relative;
    margin-top: 12px;
    float: left;
}
.default-img-bg {
    background-color: #e1e1e1;
    background-size: 100% 100%;
}
.tab-content .list-wrap .item .avatar img {
    background-color: transparent;
    height: 90px;
}
.tab-content .list-wrap .item .content-wrapper {
    padding: 12px 14px 12px 0;
    margin-left: 74px;
    height: 90px;
    max-height: 90px;
    position: relative;
}
.tab-content .list-wrap .item .content {
    padding-right: 5px;
    margin-right: 48px;
    overflow: hidden;
}
.tab-content .list-wrap .item .movie-title {
    max-height: 24px;
    margin-bottom: 7px;
    line-height: 24px;
    overflow: hidden;
}

.box-flex {
    display: -webkit-box;
    display: flex;
}
.tab-content .list-wrap .item .detail {
    box-sizing: border-box;
    line-height: 1;
    overflow: hidden;
}
.tab-content .list-wrap .item .title {
    font-size: 17px;
    color: #333;
    font-weight: 700;
    padding-right: 5px;
    flex-shrink: 1;
}

.line-ellipsis {
    text-overflow: ellipsis;
    overflow: hidden;
    white-space: nowrap;
}
.tab-content .list-wrap .item .detail {
    box-sizing: border-box;
    line-height: 1;
    overflow: hidden;
}

.footerTab, a, div {
    -webkit-tap-highlight-color: transparent;
}
.line-ellipsis {
    text-overflow: ellipsis;
    overflow: hidden;
    white-space: nowrap;
}
.actor, .tab-content .list-wrap .item .detail .score, .tab-content .list-wrap .item .detail .show-date, .tab-content .list-wrap .item .detail .show-info {
    font-size: 13px;
    color: #666;
}
.tab-content .list-wrap .item .detail .score .grade {
    font-weight: 700;
    color: #faaf00;
    font-size: 15px;
}
.tab-content .list-wrap .item .detail .actor, .tab-content .list-wrap .item .detail .score, .tab-content .list-wrap .item .detail .show-date, .tab-content .list-wrap .item .detail .show-info {
    font-size: 13px;
    color: #666;
}

.tab-content .list-wrap .item .detail>div+div {
    margin-top: 6px;
    line-height: 15px;
}
.tab-content .list-wrap .item .detail .actor, .tab-content .list-wrap .item .detail .score, .tab-content .list-wrap .item .detail .show-date, .tab-content .list-wrap .item .detail .show-info {
    font-size: 13px;
    color: #666;
}
.tab-content .list-wrap .item .detail>div+div {
    margin-top: 6px;
    line-height: 15px;
}

.line-ellipsis {
    text-overflow: ellipsis;
    overflow: hidden;
    white-space: nowrap;
}
.tab-content .list-wrap .item .button-block {
    font-size: 12px;
    position: absolute;
    right: 14px;
    top: 0;
    bottom: 0;
    height: 27px;
    margin: auto;
}
.tab-content .list-wrap .item .button-block .btn {
    width: 47px;
    height: 27px;
    line-height: 28px;
    text-align: center;
    box-sizing: border-box;
    background-color: #f03d37;
    color: #fff;
    border-radius: 4px;
    white-space: nowrap;
    font-size: 12px;
    cursor: pointer;
}
.tab-content .list-wrap .item .button-block .btn {
    width: 47px;
    height: 27px;
    line-height: 28px;
    text-align: center;
    box-sizing: border-box;
    background-color: #f03d37;
    color: #fff;
    border-radius: 4px;
    white-space: nowrap;
    font-size: 12px;
    cursor: pointer;
}
</style>


