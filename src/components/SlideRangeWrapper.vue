<template>
  <div class="slide-range-wrapper">
    <div class="slide-ranger">
      <div class="title">Range Slider</div>
      <div class="body">
        <pre class="mr-1">{{ min }}</pre>
        <input
          type="range"
          v-model="value"
          :min="min"
          :max="max"
          :step="steps"
          @change="$emit('onchange', 1)"
          class="pa-1"
        />
        <pre class="ml-1">{{ max }}</pre>
      </div>
      <pre>Value: {{ value }}</pre>
    </div>

    <div class="body">
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
export default {
  name: "SlideRangeWrapper",
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
.slide-range-wrapper .body {
  display: flex;
  justify-content: center;
  align-items: center;
}
.slide-range-wrapper .slide-range-wrapper-form {
  width: 25%;
  text-align: left;
  margin-right: 1rem;
}

.slide-range-wrapper .code-block .title {
	font-size: 1.2rem;
	font-style: italic;
}
.slide-range-wrapper .code-block .code {
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
.pa-1 {
  padding: 1rem 0;
}

.slide-ranger .title {
  font-size: 2rem;
  padding: 1rem 0;
}

.slide-ranger .body {
  display: flex;
  justify-content: center;
  align-items: center;
}

/* slider bar */
input[type="range"] {
  background: transparent;
  -webkit-appearance: none;
  width: 20%;
  transition: 0.4s all ease-out;
}

input[type="range"]:focus {
  outline: none; /* Removes the blue border. You should probably do some kind of focus styling for accessibility reasons though. */
}
/* slider thumb */
input[type="range"]::-webkit-slider-thumb {
  -webkit-appearance: none;

  border: 1px solid #000000;
  height: 15px;
  width: 15px;
  border-radius: 25%;
  background: #1208ad;
  cursor: pointer;
  margin-top: -4px;
  box-shadow: 1px 1px 1px #000000, 0px 0px 1px #0d0d0d;
  transition: 0.4s all ease-out;
}

input[type="range"]::-webkit-slider-runnable-track {
  width: 100%;
  height: 8.4px;
  cursor: pointer;
  box-shadow: 1px 1px 1px #000000, 0px 0px 1px #0d0d0d;
  background: #06b49d;
  border-radius: 1.3px;
  border: 0.2px solid #010101;
}
</style>