<template>
  <div id="app">
    <h3>default style</h3>
    <ui-slider class="default-style" :value="defaultvalue" @immediatechange="defaultValueChange"></ui-slider>
    <p>{{defaultvalue}}</p>
    <h3>step 0.01</h3>
    <ui-slider class="default-style" :value="stepvalue" :step="step" @immediatechange="stepValueChange"></ui-slider>
    <p>{{stepvalue}}</p>
    <h3>value 30</h3>
    <ui-slider class="default-style" :value="customvalue" @immediatechange="customValueChange"></ui-slider>
    <p>{{customvalue}}</p>
    <h3>max 300</h3>
    <ui-slider class="default-style" :value="maxvalue" :max="max" @immediatechange="maxValueChange"></ui-slider>
    <p>{{maxvalue}}</p>
    <h3>full width</h3>
    <ui-slider class="full-width" :value="fullwidthvalue" @immediatechange="fullWidthValueChange"></ui-slider>
    <p>{{fullwidthvalue}}</p>
  </div>
</template>

<script>
import UiSlider from '../node_modules/anu-ui-slider/anu-ui-slider.vue'

export default {
  components: {
    UiSlider
  },
  data() {
    return {
      defaultvalue: 0,
      customvalue: 30,
      step: 0.01,
      stepvalue: 0,
      maxvalue: 0,
      max: 300,
      fullwidthvalue: 0
    }
  },
  methods: {
    defaultValueChange: function (value) {
      this.defaultvalue = parseFloat(value);
    },
    customValueChange: function (value) {
      this.customvalue = parseFloat(value);
    },
    stepValueChange: function (value) {
      this.stepvalue = parseFloat(value);
    },
    maxValueChange: function (value) {
      this.maxvalue = parseFloat(value);
    },
    fullWidthValueChange: function (value) {
      this.fullwidthvalue = parseFloat(value);
    }
  }
}
</script>

<style lang="scss">
@import "../node_modules/anu-ui-slider/anu-ui-slider.scss";

body {
  margin: 0;
  padding-left:15px;
  padding-right:15px;
}

// 不推荐直接给元素上样式
.default-style {
  @include anu-ui-slider((
    width: 256px,
    height: 16px
  ));
}

.full-width {
  @include anu-ui-slider((
    width: 100%,
    height: 16px
  ));
}

</style>
