<template>
  <div class="container mx-auto sm:flex py-5 sm:py-10 mt-10 sm:mt-20">
    <!-- Contact form start -->
    <div class="w-full sm:w-1/2">
      <div class="leading-loose">
        <form
          class="max-w-xl m-4 p-6 sm:p-10 bg-secondary-light dark:bg-secondary-dark rounded-xl shadow-xl text-left"
          ref="form"
        >
          <p
            class="text-primary-dark dark:text-primary-light text-2xl font-semibold mb-8"
          >
            Contact Form
          </p>
          <div class="">
            <label
              class="block text-lg text-primary-dark dark:text-primary-light mb-2"
              for="name"
              >Full Name</label
            >
            <input
              class="w-full px-5 py-2 border-0 text-primary-dark dark:text-secondary-light bg-ternary-light dark:bg-ternary-dark rounded-md shadow-sm text-md dark:font-medium"
              id="name"
              name="name"
              v-model="form.name"
              type="text"
              required=""
              placeholder="Your Name"
              aria-label="Name"
            />
          </div>
          <div class="mt-6">
            <label
              class="block text-lg text-primary-dark dark:text-primary-light mb-2"
              for="email"
              >Email</label
            >
            <input
              class="w-full px-5 py-2 border-0 text-primary-dark dark:text-secondary-light bg-ternary-light dark:bg-ternary-dark rounded-md shadow-sm text-md dark:font-medium"
              id="email"
              name="email"
              v-model="form.email"
              type="text"
              required=""
              placeholder="Your Email"
              aria-label="Email"
            />
          </div>
          <div class="mt-6">
            <label
              class="block text-lg text-primary-dark dark:text-primary-light mb-2"
              for="subject"
              >Subject</label
            >
            <input
              class="w-full px-5 py-2 border-0 text-primary-dark dark:text-secondary-light bg-ternary-light dark:bg-ternary-dark rounded-md shadow-sm text-md dark:font-medium"
              id="subject"
              name="subject"
              v-model="form.subject"
              type="text"
              required=""
              placeholder="Subject"
              aria-label="Subject"
            />
          </div>

          <div class="mt-6">
            <label
              class="block text-lg text-primary-dark dark:text-primary-light mb-2"
              for="message"
              >Message</label
            >
            <textarea
              class="w-full px-5 py-2 border-0 text-primary-dark dark:text-secondary-light bg-ternary-light dark:bg-ternary-dark rounded-md shadow-sm text-md dark:font-medium"
              id="message"
              name="message"
              v-model="form.message"
              cols="14"
              rows="6"
            ></textarea>
          </div>

          <div class="mt-6">
            <button
              class="px-4 py-2.5 text-white font-medium tracking-wider bg-indigo-500 hover:bg-indigo-600 rounded-lg"
              type="submit"
              @click="submit"
            >
              Send Message
            </button>
          </div>
        </form>
      </div>
    </div>
    <!-- Contact form end -->

    <!-- Contact details start -->
    <div class="w-full sm:w-1/2">
      <div class="text-left max-w-xl px-6">
        <h2
          class="text-2xl text-primary-dark dark:text-primary-light font-semibold mt-12 mb-8"
        >
          Contact details
        </h2>
        <ul class="">
          <li class="flex" v-for="contact in contacts" :key="contact.id">
            <i
              :data-feather="contact.icon"
              class="w-5 text-gray-500 dark:text-gray-400 mr-4"
            ></i>
            <p class="text-lg mb-4 text-ternary-dark dark:text-ternary-light">
              {{ contact.name }}
            </p>
          </li>
        </ul>
      </div>
    </div>
    <!-- Contact details end -->
  </div>
</template>

<script>
import feather from "feather-icons";
import axios from "axios";

export default {
  data: () => {
    return {
      form: {
        name: "",
        email: "",
        subject: "",
        message: ""
      },
      contacts: [
        {
          id: 1,
          name: "Oshué, KasaVubu - Kinshasa",
          icon: "map-pin"
        },
        {
          id: 2,
          name: "me@abarchibody.com",
          icon: "mail"
        },
        {
          id: 3,
          name: "+243 81 20 44 091",
          icon: "phone"
        }
      ]
    };
  },
  mounted() {
    feather.replace();
  },
  updated() {
    feather.replace();
  },
  methods: {
    submit(e) {
      e.preventDefault();

      axios.post("/api/contact", this.form).then(response => {
        this.$toast.open({
          message: response.data.message,
          type: "success"
        });
      });
    }
  }
};
</script>
