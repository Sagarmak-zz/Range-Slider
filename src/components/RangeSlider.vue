<template>
  <div class="range-slider">
    <input
      type="range"
      :value="value"
      @input="$emit('input', $event.target.value)"
			:min="min"
			:max="max"
			:step="steps"
      class="pa-1"
    />
  </div>
</template>
<script>
export default {
  name: "RangeSlider",
  data() {
    return {
      value: 0,
      minValue: 0,
      maxValue: 100,
      stepsValue: 1
    };
	},
	props: ['min', 'max', 'steps', 'on-change']
};
</script>

<style>
.range-slider {
  width: 20%;
}

.pa-1 {
  padding: 1rem 0;
}

/* slider bar */
input[type="range"] {
  background: transparent;
  -webkit-appearance: none;
  width: 100%;
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