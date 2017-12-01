<template>
  <div class="loading loading-bubbles">
    <div class="bubbles-item"></div>
    <div class="bubbles-item"></div>
    <div class="bubbles-item"></div>
    <div class="bubbles-item"></div>
    <div class="bubbles-item"></div>
    <div class="bubbles-item"></div>
    <div class="bubbles-item"></div>
    <div class="bubbles-item"></div>
  </div>
</template>
<style lang="less" scoped>
@size: 1px;
@radius: 12px;
@shallow: 3px;
@c-basic: #666;

.loading {
  position: relative;
  width: 24px;
  height: 24px;
  animation: loading-rotating linear 2.5s infinite;
}

.loading-bubbles .bubbles-item {
  position: absolute;
  width: 1px;
  height: 1px;
  border-radius: 50%;
  top: 50%;
  left: 50%;
  background-color: @c-basic;
  animation: loading-bubbles linear .75s infinite;
  &:first-child {
    margin-top: -@size/2 + -@radius;
    margin-left: -@size/2;
  }
  &:nth-child(2) {
    margin-top: -@size/2 + -@radius * .73;
    margin-left: -@size/2 + @radius * .73;
  }
  &:nth-child(3) {
    margin-top: -@size/2;
    margin-left: -@size/2 + @radius;
  }
  &:nth-child(4) {
    margin-top: -@size/2 + @radius * .73;
    margin-left: -@size/2 + @radius * .73;
  }
  &:nth-child(5) {
    margin-top: -@size/2 + @radius;
    margin-left: -@size/2;
  }
  &:nth-child(6) {
    margin-top: -@size/2 + @radius * .73;
    margin-left: -@size/2 + -@radius * .73;
  }
  &:nth-child(7) {
    margin-top: -@size/2;
    margin-left: -@size/2 + -@radius;
  }
  &:last-child {
    margin-top: -@size/2 + -@radius * .73;
    margin-left: -@size/2 + -@radius * .73;
  }
}

.loading-bubbles .bubbles-item {
  @delay: .093s;
  position: absolute;
  top: 50%;
  left: 50%;
  display: inline-block;
  border-radius: 50%;
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
  &:nth-child(6) {
    animation-delay: @delay * 5;
  }
  &:nth-child(7) {
    animation-delay: @delay * 6;
  }
  &:last-child {
    animation-delay: @delay * 7;
  }
}



@keyframes loading-bubbles {
  0% {

    box-shadow: 0 0 0 3px #666;
  }
  90% {
    box-shadow: 0 0 0 0 #666;
  }
  100% {
    box-shadow: 0 0 0 3px #666;
  }
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
