<template>
  <div class="loading loading-lines">
    <div class="lines-item"></div>
    <div class="lines-item"></div>
    <div class="lines-item"></div>
    <div class="lines-item"></div> 
  </div>
</template>
<style lang="less" scoped>
@size: 5px;
@width: 24px;
@lineheight: 16px;
@shallow: 3px;
@b-basic: #000;
@c-basic: rgba(0, 0, 0, 0.2);
@delay: .12s;

.loading {
  position: relative;
  width: @width;
  height: @width;
}

.loading-lines .lines-item {
  position: absolute;
  width: 3px;
  height: @lineheight;
  border-radius: 5px;
  top: 50%;
  left: 50%;
  transform: translateY(-50%);
  background-color: @c-basic;
  animation: loading-lines linear .75s infinite;
  &:first-child {
    margin-left: -@size*2;
  }
  &:nth-child(2) {
    margin-left: -@size;
  }
  &:nth-child(3) {}
  &:nth-child(4) {
    margin-left: @size;
  }
  &:nth-child(5) {
    margin-left: @size*2;
  }
  &:nth-child(2) {
    animation-delay: @delay;
  }
  &:nth-child(3) {
    animation-delay: @delay * 2;
  }
  &:nth-child(4) {
    animation-delay: @delay * 3;
  }
  &:nth-child(5) {
    animation-delay: @delay * 4;
  }
}



@keyframes loading-lines {
  0% {
    height: 6px;
    background-color: @c-basic;
  }
  60% {
    height: @lineheight;
    background-color: @b-basic;
  }
  100% {
    height: 6px;
    background-color: @c-basic;
  }
}

</style>
