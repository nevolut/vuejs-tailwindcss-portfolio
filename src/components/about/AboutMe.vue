<template>
  <div class="block sm:flex sm:gap-10 mt-10 sm:mt-20">
    <!-- About me portfolio image start -->
    <div class="w-full sm:w-1/4 mb-7 sm:mb-0">
      <img
        src="../../assets/images/avatar.png"
        class="rounded-xl w-96"
        alt=""
      />
    </div>
    <!-- About me portfolio image end -->

    <!-- About me details start -->
    <div class="w-full sm:w-3/4 text-left">
      <p
        v-for="bio in bios"
        :key="bio.id"
        class="mb-4 text-ternary-dark dark:text-ternary-light text-lg"
      >
        {{ bio.bio }}
      </p>
    </div>
    <!-- About me details end -->
  </div>
</template>

<script>
export default {
  setup() {
    return {
      bios: [
        {
          id: 1,
          bio: "I'm Archimède Body"
        },
        {
          id: 2,
          bio:
            "I have been working as a full-stack software engineer since 2017, building high quality, scalable solutions for the web across a wide range of industries. currently living in Kinshasa, DRC. I have a Bachelor of Science in Computer Science at Bangalore University. I am both driven and self-motivated, and I am constantly experimenting with new technologies and techniques. I am very passionate about Web Development, and strive to better myself as a developer, and the development community as a whole."
        },
        {
          id: 3,
          bio:
            "Most of the people I talk with regarding the product or website that I am developing, tend to ask if I’m using any Content Management System or template builder. When I say none, they usually look very surprised and ask, “Why!? It’s far easier to use a template builder, and it saves a lot of development time”. They make me question myself again and again, but every time I confirm that I made the right decision. Each and every single line of code that makes my product alive is written by me, by my own way of thinking, and my own creative ideas. It may not be perfect, maybe even off the web guidelines."
        },
        {
          id: 4,
          bio:
            "I must admit that this did not only make my coding more efficient and manageable, but each piece of code is there because it is intended to be there. It has a meaning, its own objective. I hate to see unnecessary data in places that would only just take space. I want to be in control of each part of the process cycle. When I think about the web, I don’t just think about being efficient, but also about the load time and the weight of each request from your machine, back and forth to the server. How can we improve this? How can we make it better for the user?"
        }
      ]
    };
  }
};
</script>
