<template>
  <div class="header row align-items-center">
    <div class="col">
      <div class="d-flex justify-content-center align-items-center">
        <span class="full">FULL</span>
        <i class="bi bi-record-fill circle"></i>
        <span class="stop">STOP</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style scoped>
.full {
  color: #7bed8d;
}
.stop {
  color: #a6bcd0;
}
.header {
  background-color: #f0f4f8;
  font-size: 24pt;
  font-weight: bold;
  align-items: center;
}

.circle {
  color: #7bed8d;
  font-size: 60pt;
}
</style>
