<!--<template>
  <div class="ThreeApps-Container">
    <h1>
      تعرف علي اهم الخدمات <br />
      الي يتم تقديمها عبر البرامج الخاصة بنا
    </h1>
    <div class="ThreeApps">
      <moshafApp @mouseenter="handelFirst" :v-if="first" @mouseleave="clear">
        <template v-slot:start-div>
          <img src="../assets/moshafscreen.png" alt="" />
          <h2>الـقــرأن الكـريـم</h2>
        </template>
        <template v-slot:open-text>
          <h2>الـقــرأن الكـريـم</h2>
          <p>
            يسعاد غير القادرين علي القرائة و غير القارئين باللغة العربية علي
            استماع و حفظ القرأن الكريم بصوت قارئ عن طريق البحث بالصوت و التفاعل
            مع شاشة الجوال
          </p>
          <h3>لتحميل البرنامج اضغط هنا</h3>
        </template>
        <template v-slot:screen-content>
          <img src="../assets/moshafscreen.png" />
        </template>
      </moshafApp>
      <moshafApp v-if="secound" @mouseenter="handelSecound" @mouseleave="clear">
        <template v-slot:start-div>
          <img src="../assets/moshafscreen.png" alt="" />
          <h2>الـقــرأن الكـريـم</h2>
        </template>
        <template v-slot:open-text>
          <h2>الـقــرأن الكـريـم</h2>
          <p>
            يسعاد غير القادرين علي القرائة و غير القارئين باللغة العربية علي
            استماع و حفظ القرأن الكريم بصوت قارئ عن طريق البحث بالصوت و التفاعل
            مع شاشة الجوال
          </p>
          <h3>لتحميل البرنامج اضغط هنا</h3>
        </template>
        <template v-slot:screen-content>
          <img src="../assets/moshafscreen.png" />
        </template>
      </moshafApp>
      <moshafApp v-if="third" @mouseenter="handelThird" @mouseleave="clear">
        <template v-slot:start-div>
          <img src="../assets/moshafscreen.png" alt="" />
          <h2>الـقــرأن الكـريـم</h2>
        </template>
        <template v-slot:open-text>
          <h2>الـقــرأن الكـريـم</h2>
          <p>
            يسعاد غير القادرين علي القرائة و غير القارئين باللغة العربية علي
            استماع و حفظ القرأن الكريم بصوت قارئ عن طريق البحث بالصوت و التفاعل
            مع شاشة الجوال
          </p>
          <h3>لتحميل البرنامج اضغط هنا</h3>
        </template>
        <template v-slot:screen-content>
          <img src="../assets/moshafscreen.png" />
        </template>
      </moshafApp>
    </div>
    <img src="../assets/bc-apps.png" class="bc1" />
    <img src="../assets/bc-apps.png" class="bc2" />
    <img src="../assets/bc-line.png" class="bc3" />
    <img src="../assets/bc-line.png" class="bc4" />
  </div>
</template>

<script>
import moshafApp from "./MoshafApp.vue";

export default {
  data() {
    return {
      first: true,
      secound: true,
      third: true,
    };
  },
  methods: {
    handelFirst() {
      this.first = true;
      this.secound = false;
      this.third = false;
    },
      handelSecound() {
      this.first = false;
      this.secound = true;
      this.third = false;
    },
      handelThird() {
      this.first = false;
      this.secound = false;
      this.third = true;
    },
       clear() {
      this.first = true;
      this.secound = true;
      this.third = true;
    },
  },
  components: {
    moshafApp,
  },
};
</script>

<style>
.ThreeApps-Container {
  position: relative;
  text-align: center;
  /* padding-top:75px ; */
  width: 100%;
  height: 100vh;
  background: rgb(255, 255, 255);
  /* margin-top: 75px; */
}
.ThreeApps-Container h1 {
  padding-top: 120px;
}
.bc1 {
  position: absolute;
  bottom: 0;
  right: 0;
}
.bc2 {
  transform: scale(-1);
  position: absolute;
  top: 0;
  left: 0;
}
.bc3 {
  position: absolute;
  bottom: 0;
  left: 5%;
  height: 74.3%;
}
.bc4 {
  position: absolute;
  top: 0;
  right: 5%;
  height: 74.3%;
}
.ThreeApps {
  padding-top: 75px;
  text-align: center;
  display: flex;
  justify-content: center;
}
</style>-->
<template>
  <div class="ThreeApps-Container">
    <h1>
      تعرف علي اهم الخدمات <br />
      الي يتم تقديمها عبر البرامج الخاصة بنا
    </h1>
    <div class="ThreeApps">
      <moshafApp
        v-for="(app, index) in apps"
        :key="index"
        :xyz="index"
        :active-index="activeIndex"
        @set-active="setActive"
        :is-active="activeIndex === index"
        :class="{ hidden: activeIndex !== null && activeIndex !== index }"
        @clear-active="clearActive"
      >
        <template v-slot:start-div>
          <img :src="app.image" alt="" />
          <!-- <h2>{{ app.title }}</h2> -->
        </template>
        <template v-slot:open-text>
          <h2>{{ app.title }}</h2>
          <p>{{ app.description }}</p>
          <!-- <h3>لتحميل البرنامج اضغط هنا</h3> -->
        </template>
        <template v-slot:screen-content>
          <img :src="app.image" />
        </template>
      </moshafApp>
    </div>
    <img src="../assets/bc-apps.png" class="bc1" />
    <img src="../assets/bc-apps.png" class="bc2" />
    <img src="../assets/bc-line.png" class="bc3" />
    <img src="../assets/bc-line.png" class="bc4" />
  </div>
</template>

<script setup>
import { ref } from "vue";
import moshafApp from "./MoshafApp.vue";

const apps = ref([
  {
    title: "الـقــرأن الكـريـم",
    description:
      "يسعاد غير القادرين علي القرائة و غير القارئين باللغة العربية علي استماع و حفظ القرأن الكريم بصوت قارئ عن طريق البحث بالصوت و التفاعل مع شاشة الجوال",
    image: require("../assets/moshafscreen.png"),
  },
  {
    title: "الـقــرأن الكـريـم",
    description:
      "يسعاد غير القادرين علي القرائة و غير القارئين باللغة العربية علي استماع و حفظ القرأن الكريم بصوت قارئ عن طريق البحث بالصوت و التفاعل مع شاشة الجوال",
    image: require("../assets/moshafscreen.png"),
  },
  {
    title: "الـقــرأن الكـريـم",
    description:
      "يسعاد غير القادرين علي القرائة و غير القارئين باللغة العربية علي استماع و حفظ القرأن الكريم بصوت قارئ عن طريق البحث بالصوت و التفاعل مع شاشة الجوال",
    image: require("../assets/moshafscreen.png"),
  },
]);

const activeIndex = ref(null);

function setActive(index) {
  activeIndex.value = index;
}

function clearActive() {
  activeIndex.value = null;
}

// function setActive(index) {
//   activeIndex.value = index;
//   console.log(index);
// }

function clear() {
  activeIndex.value = null;
}
function handleEmit(id) {
  activeIndex.value = id;
}
</script>

<style scoped>
.hidden {
  display: none;
}
.ThreeApps-Container {
  position: relative;
  text-align: center;
  width: 100%;
  height: 100vh;
  background: rgb(255, 255, 255);
}
.ThreeApps-Container h1 {
  padding-top: 120px;
}
.bc1 {
  position: absolute;
  bottom: 0;
  right: 0;
  width: 20%;
}
.bc2 {
  transform: scale(-1);
  position: absolute;
  top: 0;
  left: 0;
  width: 20%;
}
.bc3 {
  position: absolute;
  bottom: 0;
  left: 5%;
  height: 63.3%;
}
.bc4 {
  position: absolute;
  top: 0;
  right: 5%;
  height: 63.3%;
}
.ThreeApps {
  padding-top: 75px;
  text-align: center;
  display: flex;
  justify-content: center;
}
@media (max-width: 768px) {
  .ThreeApps-Container {
    height: auto;
    padding-bottom: 50px;
  }
  .ThreeApps {
    display: flex;
    flex-direction: column;
    gap: 70px;
  }
  .bc1 {
    position: absolute;
    bottom: 0;
    right: 0;
  }
  .bc2 {
    transform: scale(-1);
    position: absolute;
    top: 0;
    left: 0;
  }
  .bc3 {
    position: absolute;
    bottom: 0;
    left: 5%;
    height: 72.3%;
  }
  .bc4 {
    position: absolute;
    top: 0;
    right: 5%;
    height: 72.3%;
  }
}
</style>
