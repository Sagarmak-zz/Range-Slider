<template>
  <div class="slide-ranger">
    <div class="title">Slide Ranger</div>
    <div class="body">
      <pre class="mr-1">{{ minRange }}</pre>
      <input
        type="range"
        v-model="rangeValue"
        :min="minRange"
        :max="maxRange"
        :step="rangeSteps"
        @change="$emit('onchange', 1)"
        class="pa-1"
      />
      <pre class="ml-1">{{ maxRange }}</pre>
    </div>
    <pre>Value: {{ rangeValue }}</pre>
  </div>
</template>

<script>
export default {
  name: "SlideRanger",
  created() {
    this.rangeValue = this.value;
    this.minRange = this.min;
    this.maxRange = this.max;
    this.rangeSteps = this.steps;
  },
  props: {
    value: {
      type: Number,
      required: false
    },
    min: {
      type: Number,
      required: false,
      default: 0
    },
    max: {
      type: Number,
      required: false,
      default: 100
    },
    steps: {
      type: Number,
      required: false,
      default: 1
    },
    onChange: {
      type: Function,
      required: false,
      default: () => {}
    }
  },
  data() {
    return {
      rangeValue: 0,
      minRange: 0,
      maxRange: 100,
      rangeSteps: 1
    };
  }
};
</script>
<style>
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
