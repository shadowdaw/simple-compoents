<template>
  <div class="icon">
    <div class="bar"></div>
    <div class="bar"></div>
    <div class="bar"></div>
  </div>
</template> 
<style>
.icon {
  position: relative;
  width: 18px;
  height: 16px;
}

.bar {
  position: absolute;
  display: block;
  height: 3px;
  background-color: #AAA;
}

.bar:nth-child(1) {
  top: 0;
  width: 60%;
}

.bar:nth-child(2) {
  top: 6px;
  width: 100%;
}

.bar:nth-child(3) {
  top: 12px;
  width: 80%;
}


.bar:before {
  position: absolute;
  top: 0;
  content: " ";
  display: block;
  height: 3px;
  width: 100%;
  background-color: #000;
  transition: width 300ms;
}

.icon .bar:nth-child(2):before {
  -webkit-transition-delay: 0.1s;
  transition-delay: 0.1s;
}

.icon .bar:nth-child(3):before {
  -webkit-transition-delay: 0.2s;
  transition-delay: 0.2s;
}

.icon:hover .bar:before,
.icon.active .bar:before {
  width: 0;
}

</style>
