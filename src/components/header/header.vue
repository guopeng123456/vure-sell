<template>
  <div class="header">
    <div class="content-wrapper">
    <div class="avatar">
      <img width="64" height="64" :src="seller.avatar" alt="">
    </div>
      <div class="content">
        <div class="title">
          <span class="brand"></span>
          <span class="name">{{seller.name}}</span>
        </div>
        <div class="description">
          {{seller.description}}/{{seller.deliveryTime}}分钟送达
        </div>
        <div v-if="seller.supports" class="support">
          <span class="icon" :class="classMap[seller.supports[0].type]"></span>
          <span class="text">{{seller.supports[0].description}}</span>
        </div>
      </div>
    </div>
    <div class="bullentin-wrapper">

    </div>
  </div>
</template>

<script type="text/ecmascript-6">
   export default {
     props: {
       seller: {
        type: Object
       }
     },
     created () {
       this.classMap = ['decrease', 'discount', 'special', 'invoice', 'guarantee'];
     }
   };
</script>

<style>
   .header {color : #fff;background:#000}
  .content-wrapper {padding:24px 12px 18px 24px;font-size:0}
  .avatar {display:inline-block;font-size:14px}
  img {border-radius:2px}
   .content {display:inline-block;font-size:14px;margin-left:16px}
  .title {margin:2px 0 8px 0;}
  .brand {display:inline-block;vertical-align:top;width:30px;height:18px;background:url(brand@2x.png);background-size:30px 18px;backgroumd-repeat:no-repeat}
  .name {margin-left:6px;font-size:16px;line-height:18px;font-weight:bold}
  .description {margin-bottom :10px;font-size:12px;line-height:12px}
  .support > .icon {display:inline-block;width:12px;height:12px;margin-right:4px;background-size:12px 12px;background-repeat:no-repeat;vertical-align:top}
   .support >.decrease {background:url(decrease_1@2x.png);background-repeat:no-repeat;    background-size: 12px 12px}
   .support >.discount {background:url(discount_1@2x.png);background-repeat:no-repeat;    background-size: 12px 12px  }
   .support >.guarantee {background:url(guarantee_1@2x.png);background-repeat:no-repeat;    background-size: 12px 12px}
   .support >.invoice{background:url(invoice_1@2x.png);background-repeat:no-repeat;    background-size: 12px 12px}
   .support >.special {background:url(special_1@2x.png);background-repeat:no-repeat;    background-size: 12px 12px}
   .support {font-size:12px}
   .text {line-height:12px;font-szie:12px}
</style>
