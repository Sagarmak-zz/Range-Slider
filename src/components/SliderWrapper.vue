<template>
  <div class="slide-range-wrapper">
    <div class="slide-ranger">
      <div class="title">Range Slider</div>
      <div class="body">
        <pre class="mr-1">{{ min }}</pre>
        <RangeSlider v-model="value" :min="min" :max="max" :steps="steps" @on-change="log" />
        <pre class="ml-1">{{ max }}</pre>
      </div>
      <pre>Value: {{ value }}</pre>
    </div>

    <div class="wrapper-body">
      <div class="slide-range-wrapper-form">
        <div class="form-content px-1">
          <div class="pb-1">Value:</div>
          <input v-model="value" type="text" name="minValue" placeholder="Min Value" />
        </div>
        <div class="form-content px-1">
          <div class="pb-1">Min Value:</div>
          <input v-model="min" type="text" name="minValue" placeholder="Min Value" />
        </div>
        <div class="form-content px-1">
          <div class="pb-1">Max Value:</div>
          <input v-model="max" type="text" name="maxValue" placeholder="Max Value" />
        </div>
        <div class="form-content px-1">
          <div class="pb-1">Steps:</div>
          <input v-model="steps" type="text" name="steps" placeholder="Steps" />
        </div>
      </div>
      <div class="code-block">
        <p class="title">Code:</p>
        <div class="code">
          <div class="pb-1">{{ html }}</div>
          <div class="pb-1 ml-1">{{ html2 }}</div>
          <div class="pb-1 ml-1">{{ html3 }}</div>
          <div class="pb-1 ml-1">{{ html4 }}</div>
          <div class="pb-1 ml-1">{{ html5 }}</div>
          {{ html6 }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import RangeSlider from "./RangeSlider";
export default {
  name: "SlideRangeWrapper",
  components: {
    RangeSlider
  },
  data() {
    return {
      min: 0,
      max: 100,
      steps: 1,
      value: 0
    };
  },
  methods: {
    log() {
      console.log("Changed");
    }
  },
  computed: {
    html() {
      return `<RangeSlider`;
    },
    html2() {
      return `value="${this.value}"`;
    },
    html3() {
      return `min="${this.min}"`;
    },
    html4() {
      return `max="${this.max}"`;
    },
    html5() {
      return `steps="${this.steps}"`;
    },
    html6() {
      return `/>`;
    }
  }
};
</script>

<style>
.slide-range-wrapper .slide-ranger .title {
  font-size: 2rem;
  padding: 1rem 0;
}

.slide-range-wrapper .slide-ranger .body {
  display: flex;
  justify-content: center;
  align-items: center;
}

.slide-range-wrapper .wrapper-body {
  display: flex;
  justify-content: center;
  align-items: center;
}
.slide-range-wrapper .wrapper-body .slide-range-wrapper-form {
  width: 25%;
  text-align: left;
  margin-right: 1rem;
}

.slide-range-wrapper .wrapper-body .code-block .title {
	font-size: 1.2rem;
	font-style: italic;
}
.slide-range-wrapper .wrapper-body .code-block .code {
  background: teal;
  border-radius: 5px;
  border: solid 1px #ccc;
  width: 17rem;
  height: 15rem;
  margin-left: 1rem;
  margin-top: 1rem;

  text-align: left;
  font-family: monospace;
  font-size: 1.5rem;
  padding: 2rem 3.5rem;
}

.mt-2 {
  margin-top: 2rem;
}

.px-1 {
  padding: 0.5rem 0;
}

.pb-1 {
  padding-bottom: 0.5rem;
}

input[type="text"] {
  width: 100%;
  padding: 0.6rem;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-shadow: inset 0 1px 3px #ddd;
}

.mr-1 {
  margin-right: 1rem;
}
.ml-1 {
  margin-left: 1rem;
}
</style>