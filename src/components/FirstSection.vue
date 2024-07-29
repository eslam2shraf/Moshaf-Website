<template>
  <div class="starter">
    <!-- <img src="../assets/start-image.png" alt="moshaf intro image" class="first-image"> -->
  </div>
</template>

<script>
export default {};
</script>

<style>
.starter {
  /* margin-top:75px ; */
  width: 100%;
  height: 100vh;
  background: orange;
  background-size: cover;
  flex-shrink: 0;
  background: url(../assets/start-image.png) lightgray 50% / cover no-repeat;
}
@media (max-width: 768px) {
  body {
    width: 100vw;
  }
  .starter {
    background: url(../assets/start-image.png) lightgray 50% / cover no-repeat;
    height: 50vh;
    margin-top: 50px;
  }
}
@media (max-width: 480px) {
  .starter {
    margin-top: 150px;
  }
}
</style>
