<template>
  <div class="icon">
    <i class="menu"></i>
  </div>
</template> 
<style>
.icon {
  width: 25px;
  height: 25px;
}

.menu {
  display: block;
  position: relative;
  height: 1px;
  margin: 50% 0;
  width: 100%;
  background-color: #000;
  transition: transform 300ms;
}

.menu:before,
.menu:after {
  transition: transform 300ms;
  background-color: #000;
  position: absolute;
  display: block;
  content: " ";
  width: 100%;
  height: 1px;
}

.menu:before {
  transform: translateY(-7px);
}

.menu:after {
  transform: translateY(7px);
}

.icon.active .menu,
.icon:hover .menu {
  background-color: transparent;
}

.icon.active .menu:before,
.icon:hover .menu:before {
  transform: rotate(45deg);
}

.icon.active .menu:after,
.icon:hover .menu:after {
  transform: rotate(-45deg);
}

</style>
