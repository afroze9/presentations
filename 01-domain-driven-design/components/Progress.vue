<template>
  <LightOrDark>
    <template #light>
      <div class="progress-container-light">
        <div class="progress" :style="{ width: percentage + '%' }"></div>
      </div>
    </template>
    <template #dark>
      <div class="progress-container-dark">
        <div class="progress" :style="{ width: percentage + '%' }"></div>
      </div>
    </template>
  </LightOrDark>
</template>

<script>
export default {
  props: {
    percentage: {
      type: Number,
      required: true,
      validator: value => value >= 0 && value <= 100
    }
  }
};
</script>

<style scoped>
.progress-container-light {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 2px;
  background-color: #f0f0f0;
}

.progress-container-dark {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 2px;
  background-color: #000000;
}

.progress {
  height: 100%;
  background-color: #4caf50;
  transition: width 0.3s ease;
}
</style>
