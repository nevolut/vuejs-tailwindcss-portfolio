<template>
  <!-- Banner start -->
  <section
    class="flex flex-col sm:justify-between items-center sm:flex-row mt-12 sm:mt-2"
  >
    <div class="w-full sm:w-1/3 text-left">
      <h1
        class="text-3xl sm:text-5xl text-center sm:text-left font-semibold text-ternary-dark dark:text-primary-light uppercase"
      >
        Hi, Iam Body
      </h1>
      <p
        class="mt-4 text-2xml sm:text-4xl text-center sm:text-left font-semibold leading-none text-gray-400"
      >
        A software engineer
      </p>
      <div class="flex justify-center sm:block">
        <a
          href="/cv"
          class="flex justify-center items-center w-36 sm:w-48 mt-12 mb-6 sm:mb-0 text-lg border border-indigo-200 dark:border-ternary-dark py-2.5 sm:py-3 shadow-lg rounded-xl bg-indigo-50 hover:bg-indigo-500 text-gray-500 hover:text-white"
        >
          <span class="text-sm sm:text-lg">View CV</span></a
        >
      </div>
    </div>
    <div class="w-full sm:w-2/3 text-right float-right mt-8 sm:mt-0">
      <img
        v-if="theme === 'light'"
        src="@/assets/images/developer.svg"
        alt="Developer"
      />
      <img v-else src="@/assets/images/developer-dark.svg" alt="Developer" />
    </div>
  </section>
  <!-- Banner end -->
</template>

<script>
import feather from "feather-icons";

export default {
  name: "Home",
  data: () => {
    return {
      theme: ""
    };
  },
  created() {
    this.theme = localStorage.getItem("theme") || "light";
  },
  mounted() {
    feather.replace();
    this.theme = localStorage.getItem("theme") || "light";
  },
  updated() {
    feather.replace();
  },
  methods: {}
};
</script>

<style scoped></style>
