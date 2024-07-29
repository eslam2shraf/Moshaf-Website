<template>
  <AppDescription v-for="(app, index) in apps" :key="index" :rightStart="app?.rightStart">
  <template v-slot:title>
          <h2>{{ app?.title }}</h2>
        </template>
        <template v-slot:text>
          <p>{{ app?.description }}</p>
          <h3>لتحميل البرنامج اضغط هنا</h3>
        </template>
        <template v-slot:screen-content>
          <img :src="app?.image" />
        </template>
        <template v-slot:buttons>
                   <button>
              <img src="../assets/apple.svg" alt="apple">
              App Store

          </button>
            <button>
                     <img src="../assets/android.svg" alt="android">
                Google Play
                </button>
        </template>

  </AppDescription>
</template>

<script>
import AppDescription from "./AppDescription.vue";

export default {
  data() {
    return {
      apps: [
        {
          title: "الـقــرأن الكـريـم",
          description:
            "مع برنامج القراّن الكريم يمكنك قراءة السور و حفظها في المفضلة و الاستماع لها بعدة أصوات من الشيوخ المشهورين و ترجمة الايات بمختلف لغات العالم و تكبير وتصغير الخط للمساعدة في القراءة و البحث في السور و الايات واستلام الاشعارات و استعمال البرنامج بدون انترنت",
       image: require("../assets/mockup1.png"),
          rightStart: false,
        },
        {
          title: "الـقــرأن لـلأمــيين",
          description:
            "مع برنامج القراّن الكريم يمكنك قراءة السور و حفظها في المفضلة و الاستماع لها بعدة أصوات من الشيوخ المشهورين و ترجمة الايات بمختلف لغات العالم و تكبير وتصغير الخط للمساعدة في القراءة و البحث في السور و الايات واستلام الاشعارات و استعمال البرنامج بدون انترنت",
     image: require("../assets/mockup1.png"),
          rightStart: true,
        },
        {
          title: "الـقــرأن للمكفوفين",
          description:
            "مع برنامج القراّن الكريم يمكنك قراءة السور و حفظها في المفضلة و الاستماع لها بعدة أصوات من الشيوخ المشهورين و ترجمة الايات بمختلف لغات العالم و تكبير وتصغير الخط للمساعدة في القراءة و البحث في السور و الايات واستلام الاشعارات و استعمال البرنامج بدون انترنت",
           image: require("../assets/mockup1.png"),
          rightStart: false,
        },
      ],
    };
  },
  components: {
    AppDescription,
  },
};
</script>

<style></style>
