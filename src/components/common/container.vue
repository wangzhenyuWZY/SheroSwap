<template>
  <div class="totalModel" :class="`${pdd ? 'setpdd' : ''}${mobile ? ' setmobile' : ''}`">
    <div class="toal_bg">
      <slot name="title"></slot>
    <div class="modelBg" :style="{'paddingTop':top-20 +'px'}">
        <slot name="body"></slot>
    </div>
  </div>
  <div class="footer1">
      <slot name="footer" ></slot></div>
  </div>
</template>

<script>
export default {
  props: {
    top: {
      type: String,
      default: '72'
    },
    pdd: {
      type: Boolean,
      default: false
    },
    mobile: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style lang="scss" scoped>
.totalModel{
  max-width: 480px;
  margin: 0 auto;

  position: relative;

}
.setpdd{
  padding-bottom: 230px;
}
.toal_bg {
  position:relative;
  z-index:2;
  background: #142028;
  border-radius: 20px;
  box-sizing: border-box;
  // margin-top: 115px;
  .modelBg {
    padding: 0 20px;
  }
}
.footer1{
  border-radius:20px;
  overflow:hidden;
  background:#23323C;
position: relative;
    top: -30px;
    padding-top: 30px;
    z-index: 1;
}

@media screen and (max-width: 750px)  {

  .totalModel{
    max-width: 100%;
    padding-bottom: 20px;
     .modelBg{
        padding: 0 0.35rem;
      }
  }

    .setpdd{
      // padding: 0 0.4rem ;
      // padding-left: 0.4rem;
      // padding-right: 0.4rem;
    }
    .setmobile{
   padding-left: 0.4rem;
  padding-right: 0.4rem;
}

}
@media screen and (max-width: 375px)  {

}
</style>
