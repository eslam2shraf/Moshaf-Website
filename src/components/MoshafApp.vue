<template>
  <transition :duration="{ enter: 500, leave: 0 }">
    <div class="apps-Containers">
      <div v-if="!isActive" class="moshaf-container" @mouseenter="handleHover">
        <slot name="start-div"></slot>
      </div>
      <transition name="slide">
        <div
          class="moshaf-container-opend"
          v-if="isActive"
          @mouseleave="handleHoverBack"
        >
          <div class="text-moshaf-container">
            <div class="moshaf-container-opend-text">
              <slot name="open-text"></slot>
            </div>

            <div class="buttons-container">
              <button class="download-btton">App Store</button>
              <button class="download-btton">Google Play</button>
            </div>
          </div>
          <div class="moshaf-opend-img">
            <slot name="screen-content"></slot>
          </div>
        </div>
      </transition>
    </div>
  </transition>
</template>

<script>
export default {
  data() {
    return {
      FirstDivOpend: true,
      SecoundDivOpend: false,
    };
  },
  // computed: {
  //   isActive() {
  //     return this.activeIndex === this.xyz;
  //   },
  // },
  methods: {
    handleHover() {
      this.$emit("set-active", this.xyz);
      console.log(this.xyz);
    },
    handleHoverBack() {
      this.$emit("clear-active");
    },
  },
  created() {
    console.log("xyz:", this.xyz);
  },
  props: {
    xyz: {
      type: Number,
      require: true,
    },
    isActive: {
      type: Boolean,
      default: false,
    },
    activeIndex: {
      type: Number,
      required: false,
      default: null,
    },
  },
};
</script>

<style>
/* .hidden {
  display: none;
} */

.slide-enter-from {
  opacity: 0;
  width: 0%;
}
.slide-enter-to {
  opacity: 1;
  width: 100%;
}
.slide-enter-active {
  transition: all 0.5 ease-in;
}

.slide-leave-from {
  opacity: 1;
  width: 100%;
}
.slide-leave-to {
  opacity: 0;
  width: 0%;
}
.slide-leave-active {
  transition: none;
}

.apps-Containers {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.moshaf-container {
  width: 50%;
}
.moshaf-container img {
  width: 100%;
}
.moshaf-container h2 {
  padding-top: 16px;
}
.moshaf-container-opend {
  display: flex;
  justify-content: space-evenly;
  width: 80%;

  border-radius: 8px;
  background: url(../assets/bc5.png) lightgray 50% / cover no-repeat;
  transition-property: width;
  transition-duration: 2s;
  transition-timing-function: linear;
  transition-delay: 1s;
}
.moshaf-opend-img {
  width: 80%;
}
.moshaf-container-opend img {
  width: 50%;
  margin: 40px 0px;
}
.moshaf-container-opend h2 {
  color: #000;
  font-family: "Simplified Arabic";
  font-size: 50px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
  text-align: right;
  padding-top: 40px;
}
.moshaf-container-opend h3 {
  color: #000;
  font-family: "Simplified Arabic";
  font-size: 30px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
  text-align: right;
}
.moshaf-container-opend p {
  max-width: 100%;
  color: #000;
  text-align: right;
  font-family: "Simplified Arabic";
  font-size: 32px;
  font-style: normal;
  font-weight: 400;
  line-height: 150.186%; /* 36.859px */
  padding: 20px 0px;
}
.moshaf-container-opend-text {
  margin: auto 0px;
  padding: 0px 30px;
  display: flex;
  flex-direction: column;
  align-content: flex-start;
  justify-content: center;
}
.download-btton {
  width: 250px;
  height: 85px;

  /* color: #000; */
  font-family: Arial;
  font-size: 32px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
  border-radius: 16px;
  background-color: #fff;
  border: none;
}
.buttons-container {
  margin: 0 auto;
  margin-top: 40px;
  width: 80%;
  display: flex;
  justify-content: space-around;
  margin-top: 100px;
}
.slide-enter-active {
  transition: all 0.3s ease-out;
}

.slide-leave-active {
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide-enter-from,
.slide-leave-to {
  transform: translateX(20px);
  opacity: 0;
}
@media (max-width: 768px) {
  .moshaf-container-opend {
    width: 80%;
    display: flex;
    flex-direction: column-reverse;
    justify-content: center;
    align-items: center;
  }
  .moshaf-container-opend-text {
    width: 80%;
    padding: 0;
    display: flex;
    flex-direction: column;
    align-content: center;
    justify-content: center;
  }
  .moshaf-container-opend-text h2 {
    color: #000;
    font-family: "Simplified Arabic";
    font-size: 50px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    text-align: center;
    padding-top: 0px;
  }
  .moshaf-container-opend-text p {
    text-align: center;
  }
  .text-moshaf-container {
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
  }
  .buttons-container {
    margin: 0 auto;
    margin-top: 40px;
    width: 80%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 40px;
    margin-bottom: 40px;
  }
  .download-btton {
    width: 100%;
    height: 85px;

    /* color: #000; */
    font-family: Arial;
    font-size: 32px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    border-radius: 16px;
    background-color: #fff;
    border: none;
  }
}
</style>
