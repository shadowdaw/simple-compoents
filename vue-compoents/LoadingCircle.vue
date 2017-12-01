<template>
  <div class="loading loading-circle">
  </div>
</template>
<style lang="less" scoped>
@size: 1px;
@radius: 14px;
@shallow: 3px;
@c-basic: #666;

.loading {
  position: relative;
  width: @radius *2;
  height: @radius *2;
  border: 1px solid #666;
  border-radius: 50%;
  animation: loading-rotating ease 1.5s infinite;
}

.loading-circle:before {
  position: absolute;
  content: " ";
  width: 2px;
  height: 2px;
  border-radius: 50%;
  top: -1px;
  left: 50%;
  background-color: @c-basic;
  box-shadow: 0 0 0 2px #666;
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
