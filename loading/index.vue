<template>
  <div class="loading-wrap" v-if="visible">
    <div class="loading-item">
      <div class="loading-item-dot"></div>
      <div class="loading-item-dot"></div>
      <div class="loading-item-dot"></div>
      <div class="loading-item-dot"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MyLoading',
  data() {
    return {
      visible: false,
    }
  },
}
</script>

<style lang="less" scoped>
.loading-wrap {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  z-index: 100;
  background-color: rgba(0, 0, 0, 0.1);
  display: flex;
  align-items: center;
  justify-content: center;
  // min-height: 60px;
  .loading-item {
    position: relative;
    width: 24px;
    height: 24px;
    transform: rotate(0deg);
    animation: loading 1s linear infinite;
    &-dot {
      position: absolute;
      width: 8px;
      height: 8px;
      background-color: #1890ff;
      border-radius: 100%;
    }
    .loading-item-dot:nth-child(1) {
      opacity: 0.3;
      top: 0;
      left: 0;
    }
    .loading-item-dot:nth-child(2) {
      opacity: 0.5;
      top: 0;
      right: 0;
    }
    .loading-item-dot:nth-child(3) {
      opacity: 0.7;
      bottom: 0;
      left: 0;
    }
    .loading-item-dot:nth-child(4) {
      bottom: 0;
      right: 0;
    }
  }
  @keyframes loading {
    0% {
      transform: rotate(0deg);
    }
    50% {
      transform: rotate(180deg);
    }
    100% {
      transform: rotate(360deg);
    }
  }
}
@media screen and (min-width: 800px) {
  .loading-item {
    width: 30px!important;
    height: 30px!important;
  }
  .loading-item-dot {
    width: 10px!important;
    height: 10px!important;
  }
}
</style>
