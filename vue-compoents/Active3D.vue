<template>
  <div class="active3d" @mousemove="handleTransform" @mouseleave="handleLeave" :style="{transform:`rotateX(${rotate.x}deg) rotateY(${rotate.y}deg)`}">
    <div class="banner-3d-shadow" style="transition: opacity 0.3s ease-in-out, transform 0.3s ease-in-out;" :style="{transform:`translate3d(${-5*rotateY}px,${2*rotateX}px,0)`}"></div>
    <slot></slot>
  </div>
</template>
<script>
import TWEEN from 'tween';
export default {
  data: function() {
    return {
      center: {
        x: 0,
        y: 0
      },
      rotateX: 0,
      rotateY: 0,
      rotate: {
        x: 0,
        y: 0
      }
    }
  },
  watch: {
    rotateX: function(newValue, oldValue) {
      this.tweenX(oldValue, newValue)
    },
    rotateY: function(newValue, oldValue) {
      this.tweenY(oldValue, newValue)
    }
  },
  mounted: function() {
    let left = this.$el.offsetLeft;
    let top = this.$el.offsetTop;
    let width = this.$el.offsetWidth;
    let height = this.$el.offsetHeight;
    this.center.x = width / 2;
    this.center.y = height / 2;
  },
  methods: {
    handleLeave: function(event) {
      this.rotateX = 0;
      // debugger
      this.rotateY = 0;
    },
    handleTransform: function(event) {
      let oX = event.offsetX;
      let oY = event.offsetY;
      this.rotateY = (oX - this.center.x) / this.$el.offsetWidth * 12;
      this.rotateX = (this.center.y - oY) / this.$el.offsetHeight * 16;
    },
    tweenX: function(startValue, endValue) {
      var vm = this;

      function animate() {
        if (vm.rotate.x != endValue) {
          requestAnimationFrame(animate);
          TWEEN.update()
        }
      }
      new TWEEN.Tween({ tweeningValue: startValue })
        .to({ tweeningValue: endValue }, 2000)
        .onUpdate(function() {
          vm.rotate.x = this.tweeningValue

        }).start()
      animate()
    },
    tweenY: function(startValue, endValue) {
      var vm = this;

      function animate() {
        if (vm.rotate.y != endValue) {
          requestAnimationFrame(animate);
          TWEEN.update()
        }
      }
      new TWEEN.Tween({ tweeningValue: startValue })
        .to({ tweeningValue: endValue }, 500)
        .onUpdate(function() {
          vm.rotate.y = this.tweeningValue

        }).start()
      animate()
    }
  }
}

</script>
<style>
.active3d {
  width: 100%;
  height: 500px;
  position: relative;
  perspective: 3000px;
}

</style>
