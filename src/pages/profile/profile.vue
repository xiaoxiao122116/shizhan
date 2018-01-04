<template>
  <div class="profile_page">
    <head-top headTitle="我的E宠"></head-top>

    <section>
      <section class="profile-number">
        <router-link :to="userInfo&&userInfo.user_id? '/profile/info' : '/login'" class="profile-link">
          <img :src="imgBaseUrl + userInfo.avatar" class="privateImage" v-if="userInfo&&userInfo.user_id">
          <span class="privateImage" v-else>
            <svgImage className="privateImage-svg" type="#icon-person"/>
          </span>
          <div class="user-info">
            <p>{{username}}</p>
            <p>
              <span class="user-icon">
                <svgImage className="icon-mobile" type="#icon-shouji"/>
              </span>
              <span class="icon-mobile-number">{{mobile}}</span>
            </p>
          </div>
          <span class="arrow">
            <svgImage type="#icon-jiantou1"/>
          </span>
        </router-link>
      </section>

      <section class="info-data">
        <ul class="clear">
          <router-link to="/balance" tag="li" class="info-data-link">
            <span class="info-data-top"><b>{{parseInt(balance).toFixed(2)}}</b>元</span>
            <span class="info-data-bottom">我的余额</span>
          </router-link>
          <router-link to="/benefit" tag="li" class="info-data-link">
            <span class="info-data-top"><b>{{count}}</b>个</span>
            <span class="info-data-bottom">我的优惠</span>
          </router-link>
          <router-link to="/points" tag="li" class="info-data-link">
            <span class="info-data-top"><b>{{pointNumber}}</b>分</span>
            <span class="info-data-bottom">我的积分</span>
          </router-link>
        </ul>
      </section>

      <section class="profile-1reTe">
        <!-- 我的订单 -->
        <router-link to='/order' class="myorder">
          <aside>
            <svgImage type="#icon-order-s"/>
          </aside>
          <div class="myorder-div">
            <span>分类</span>
            <span class="myorder-divsvg">
              <svgImage type="#icon-jiantou1" />
            </span>
          </div>
        </router-link>
        <!-- 积分商城 -->
        <a href='https://home.m.duiba.com.cn/#/chome/index' class="myorder">
          <aside>
            <svgImage type="#icon-jifen"/>
          </aside>
          <div class="myorder-div">
            <span>积分商城</span>
            <span class="myorder-divsvg">
              <svgImage type="#icon-jiantou1"/>
            </span>
          </div>
        </a>
        <!-- 硅谷外卖会员卡 -->
        <router-link to='/vipcard' class="myorder">
          <aside>
            <svgImage type="#icon-vip"/>
          </aside>
          <div class="myorder-div">
            <span>硅谷外卖会员卡</span>
            <span class="myorder-divsvg">
              <svgImage type="#icon-jiantou1"/>
            </span>
          </div>
        </router-link>
      </section>

      <section class="profile-1reTe">
        <!-- 服务中心 -->
        <router-link to='/service' class="myorder">
          <aside>
            <svgImage type="#icon-fuwu"/>
          </aside>
          <div class="myorder-div">
            <span>服务中心</span>
            <span class="myorder-divsvg">
              <svgImage type="#icon-jiantou1"/>
            </span>
          </div>
        </router-link>
      </section>
    </section>
  </div>
</template>

<script>

</script>

<style lang="stylus" rel="stylesheet/stylus">

</style>
