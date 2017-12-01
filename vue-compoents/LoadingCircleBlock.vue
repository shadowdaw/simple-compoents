<template>
  <div class="loading loading-circle-block">
  </div>
</template>
<style lang="less" scoped>
@size: 1px;
@radius: 14px;
@shallow: 3px;
@c-basic: rgba(96, 96, 96, 0.5);

.loading {
  position: relative;
  width: @radius *2;
  height: @radius *2;
  border: 2px solid @c-basic;
  border-radius: 50%;
  animation: loading-rotating linear 1.5s infinite;
}

.loading-circle-block {
  border-left-color: #000;
}

@keyframes loading-rotating {
  0% {
    transform: rotate(0);
  }
  100% {
    transform: rotate(360deg);
  }
}

</style>
