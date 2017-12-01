<template>
  <div class="cardbox">
    <slot></slot>
    <p>{{title}}</p>
  </div>
</template>
<script>
export default {
  props: ['title']
}

</script>
<style scoped>
.cardbox {
  margin: 0 10px;
  width: 80px;
  height: 80px;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  text-align: center;
  border: 1px solid #CCC;
  border-radius: 5px;
  box-shadow: 3px 3px 4px 2px rgba(0, 0, 0, .05);
  -webkit-box-shadow: 3px 3px 4px 2px rgba(0, 0, 0, .05);
  -moz-box-shadow: 3px 3px 4px 2px rgba(0, 0, 0, .05);
  -ms-box-shadow: 3px 3px 4px 2px rgba(0, 0, 0, .05);
  -o-box-shadow: 3px 3px 4px 2px rgba(0, 0, 0, .05);
}

</style>
