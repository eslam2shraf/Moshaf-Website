<template>
  <div :class="['quranContainer', { quranContainerReversed: rightStart }]">
    <div class="quran-header">
      <img src="../assets/line1.png" alt="" class="linedash" />
      <slot name="title"> </slot>
      <img src="../assets/line1.png" alt="" class="linedash" />
    </div>
    <div :class="['quran-content', { quranContentReverse: rightStart }]">
      <div class="text-content">
        <div class="text">
          <slot name="text"></slot>
        </div>

        <div class="quran-buttons">
          <slot name="buttons"></slot>
        </div>
      </div>
      <div class="mockup"><slot name="screen-content"></slot></div>
    </div>
    <img src="../assets/line2.svg" alt="" class="linebtm" />
  </div>
  <!-- =============================================================== -->
  <!-- <div class="quran-container quran-container-reversed" v-if="rightStart">
    <div class="quran-header">
      <img src="../assets/line1.png" alt="" />
      <slot name="title"> </slot>
      <img src="../assets/line1.png" alt="" />
    </div>
    <div class="quran-content quran-content-reverse">
      <div class="mockup"><slot name="screen-content"></slot></div>
      <div class="text-content">
        <div class="text">
          <slot name="text"></slot>
        </div>

        <div class="quran-buttons">
          <slot name="buttons"></slot>
        </div>
      </div>
    </div>
    <img src="../assets/line2.svg" alt="" />
  </div> -->
</template>

<script>
export default {
  props: {
    rightStart: {
      type: Boolean,
      required: true,
    },
  },
};
</script>

<style>
.quranContainer {
  /* width: 100vw; */
  padding-top: 80px;
  height: 80vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 0px;
}
.quranContainerReversed {
  background-color: white;
  display: flex;
  flex-direction: column;
}
.quran-header {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 24px;
  color: #000;
  text-align: center;
  font-family: "Simplified Arabic";
  font-size: 28px;
  font-style: normal;
  font-weight: 400;
  line-height: 166.053%; /* 79.706px */
}
.quran-content {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
.linebtm {
  margin-top: 40px;
  width: 100%;
}
.quranContentReverse {
  display: flex;
  flex-direction: row-reverse;
  justify-content: space-between;
}
.mockup {
  width: fit-content;
}
.mockup img {
  width: 650px;

  flex-shrink: 0;
}
.linedash {
  width: 20%;
  opacity: 0.7;
}
.text-content {
  margin-top: 100px;
  width: 55%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-items: center;
  gap: 40px;
}
.text {
  width: 90%;
  color: #000;
  text-align: right;
  font-family: "Simplified Arabic";
  font-size: 32px;
  font-style: normal;
  font-weight: 400;
  line-height: 166.053%; /* 53.137px */
}
.quran-buttons {
  width: fit-content;
  display: flex;
  flex-direction: row;
  gap: 44px;
}
.quran-buttons button {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  gap: 16px;
  width: 289px;
  height: 91px;
  flex-shrink: 0;
  border-radius: 16px;
  background: #fff;
  color: #000;
  font-family: Arial;
  font-size: 38px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
  border: none;
  outline: none;
  cursor: pointer;
}
.quranContainerReversed button {
  background: #fef7ef;
}
.text h3 {
  margin-top: 20px;
}
@media (max-width: 960px) {
  .mockup img {
    width: 400px;
  }
  .quran-content {
    display: flex;
    flex-direction: column-reverse;
    justify-content: center;
    align-items: center;
  }
  .quranContainer {
    width: 100%;
    padding-top: 80px;
    height: fit-content;
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 0px;
  }
  .text-content {
    margin: 0;
    width: 80%;
    text-align: center;
  }
  .quran-buttons {
    width: fit-content;
    display: flex;
    flex-direction: column;
    gap: 44px;
  }
  /* .linedash {
    width: 40%;
  } */
}
/* .text {
  text-align: center;
} */

/* .quran-buttons button {
  width: 450px;
} */
@media (max-width: 480px) {
  .quran-buttons button {
    width: 230px;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    gap: 16px;

    height: 91px;
    flex-shrink: 0;
    border-radius: 16px;

    color: #000;
    font-family: Arial;
    font-size: 24px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    border: none;
    outline: none;
    cursor: pointer;
  }
  .quran-buttons img {
    width: 35px;
  }
}
</style>
