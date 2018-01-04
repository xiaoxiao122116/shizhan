<template>
  <div class="msite">

    <head-top signinUp='msite'>
      <router-link class="link_search" :to="'/search/' + geohash" slot="search">
        <svgImage className="search_guide" type="#icon-sousuo"/>
      </router-link>
      <router-link class="msite_title" to="/home" slot="msite-title">
        <span class="title_text ellipsis">{{msiteTitle}}</span>
      </router-link>
    </head-top>

    <nav class="msite_nav">
      <div class="swiper-container" v-if="foodTypes.length">
        <div class="swiper-wrapper">
          <div class="swiper-slide food_types_container"
               v-for="(itemTypes, index) in foodTypes"
               :key="index">
            <router-link class="link_to_food"
                         :to="{path: '/foodtype'}"
                         v-for="itemType in itemTypes"
                         :key="itemType.id">
              <figure>
                <img :src="imgBaseUrl + itemType.image_url">
                <figcaption>{{itemType.title}}</figcaption>
              </figure>
            </router-link>
          </div>
        </div>
        <div class="swiper-pagination"></div>
      </div>
      <img src="./fl.svg" class="fl_back" v-else>
    </nav>

    <div class="shop_list_container">
      <div class="shop_header">
        <svgImage className="shop_icon" type="#icon-xuanxiang"/>
        <span class="shop_header_title">附近商家</span>
      </div>
      <shop-list v-if="hasGetData"/>
    </div>
  </div>
</template>

<script>


</script>

<style lang="stylus" rel="stylesheet/stylus">

</style>
