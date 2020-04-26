<template>
  <div class="slide-range-wrapper">
    <SlideRanger
      :value="rangeValueGetter"
      :steps="stepsRangeValue"
      :min="minRangeValue"
      :max="maxRangeValue"
      @onchange="log()"
    />

    <div class="body">
      <div class="slide-range-wrapper-form">
        <div class="form-content px-1">
          <div class="pb-1">Min Value:</div>
          <input v-model="minRange" type="text" name="minValue" placeholder="Min Value" />
        </div>
        <div class="form-content px-1">
          <div class="pb-1">Max Value:</div>
          <input v-model="maxRange" type="text" name="maxValue" placeholder="Max Value" />
        </div>
        <div class="form-content px-1">
          <div class="pb-1">Steps:</div>
          <input v-model="rangeSteps" type="text" name="steps" placeholder="Steps" />
        </div>
      </div>
      <div class="code">
        <pre>
        {
          min: {{ minRangeValue }},
          max: {{ maxRangeValue }},
          steps: {{ stepsRangeValue }},
          value: {{ rangeValueGetter }}
        }
      </pre>
      </div>
    </div>
  </div>
</template>

<script>
import SlideRanger from "./SlideRanger";
export default {
  name: "SlideRangeWrapper",
  data() {
    return {
      minRange: 0,
      maxRange: 100,
      rangeSteps: 1,
      rangeValue: 0
    };
  },
  components: {
    SlideRanger
  },
  methods: {
    log() {
      console.log("Changed");
    }
  },
  computed: {
    minRangeValue: {
      get() {
        return +this.minRange;
      }
    },
    maxRangeValue: {
      get() {
        return +this.maxRange;
      }
    },
    stepsRangeValue: {
      get() {
        return +this.rangeSteps;
      }
    },
    rangeValueGetter: {
      get() {
        return +this.rangeValue;
      }
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
}

.slide-range-wrapper .code {
  background: lightslategray;
  border-radius: 5px;
  border: solid 1px #ccc;
  width: 17rem;
  height: 12rem;
	margin-left: 2rem;
	margin-top: 2rem;
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
</style>