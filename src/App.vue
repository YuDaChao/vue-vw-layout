<template>
  <div id="app">
    <div class="box">在Vue中使用vw</div>
    <div class="ignore">此处不需要转换为视窗单位</div>
    <div aspectratio w-100-100>
      <div aspectratio-content>
        此处主要用来处理元素容器宽高比
      </div>
    </div>
    <div class="example">处理1px</div>
  </div>
</template>

<script>
export default {
  name: 'app',
  components: {}
}
</script>

<style lang="scss">
.box {
  border: 1px solid black;
  font-size: 20px;
  line-height: 28px;
  padding: 10px;
  margin-bottom: 24px;
}
.ignore {
  font-size: 24px;
  border: 2px solid pink;
  padding: 10px;
  margin-bottom: 24px;
}
[aspectratio] {
  position: relative;
}
[aspectratio]::before {
  content: '';
  display: block;
  height: 0;
}
[aspectratio-content] {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  width: 100%;
  height: 100%;
}
[w-100-100] {
  aspect-ratio: '100:100';
}
[w-100-100] {
  background: pink;
  color: #fff;
  margin-bottom: 24px;
}

@svg 1px-border {
  height: 2px;
  @rect {
    fill: var(--color, black);
    width: 100%;
    height: 50%;
  }
}

.example {
  border-bottom: 1px solid transparent;
  border-image: svg(1px-border param(--color #00b1ff)) 2 2 stretch;
}

// @svg square {
//   @rect {
//     fill: var(--color, black);
//     width: 100%; height: 1px;
//   }
// };

// .example {
//   background: white svg(square param(--color #00b1ff))  center / cover;
// }

</style>
