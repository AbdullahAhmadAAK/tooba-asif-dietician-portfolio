<script>
  import { horizontalSectionMarginClass } from "$lib/portfolio-details";
  import { onMount } from "svelte";

  const testimonials = [
    {
      text: "...she helped me last time too, to lost weight and it actually worked, so I have again asked her to make it for me. Because I feel so comfortable telling her anyyything and she understand everything and she is so polite and so so good at her work 🤩😍",
      name: "Manahel Asif Shaykh",
      designation: "Influencer",
      image: "testimonials/animated-woman.jpg",
    },
    {
      text: "Her expertise and personalized approach have made a significant impact on my health and well-being. She truly listens and tailors advice to suit my needs. I highly recommend her to anyone seeking reliable and thoughtful nutrition support.",
      name: "Abdullah Ahmad",
      designation: "Software Engineer",
      image: "testimonials/animated-man.jpeg",
    },

    {
      text: "I have lost 2 kgs and it's only been one and a half week! The meals are so fun to make and I am enjoying following my diet plan. Definitely signing up for more!",
      name: "Rimsha Imran",
      designation: "Clinical Psychologist and NLP Coach",
      image: "testimonials/animated-woman.jpg",
    },

    {
      text: "My doctor gave me a new medicine for my diabetes but my fasting sugar levels would still remain above 120g/dl. It is the first time in so long that my fasting blood sugar was 109g/dl after beginning working with Dn. Tooba. Now I'm even more determined to continue my plan.",
      name: "Saba Aamir",
      designation: "Homemaker",
      image: "testimonials/animated-woman.jpg",
    },

    {
      text: "I recently started using Happy Gut Herbal Powder and I genuinely feel lighter and less bloated than usual and I love it!",
      name: "Nosheen Usman",
      designation: "Coordinator Montessori HSGTR Rawalpindi",
      image: "testimonials/animated-woman.jpg",
    },

    {
      text: "I mainly wanted to lose weight because it was affecting my everyday life but Dn. Tooba introduced me to nutraceuticals in my plan that even my BP is lower than usual! I still have a long way to go but I'm motivated.",
      name: "Mahwish",
      designation: "Homemaker",
      image: "testimonials/animated-woman.jpg",
    },

    {
      text: "I followed Dn. Tooba's plan for a month and my belly fat got reduced by one belt hole! I feel great.",
      name: "Kashif Abbasi",
      designation: "Not Specified",
      image: "testimonials/animated-man.jpeg",
    },
  ];

  let currentIndex = 0;
  let testimonialsToShow = 3; // Default to desktop count

  function goLeft() {
    if (currentIndex > 0) {
      currentIndex = currentIndex - testimonialsToShow;
    }
  }

  function goRight() {
    if (currentIndex < testimonials.length - 1) {
      currentIndex = (currentIndex + testimonialsToShow) % testimonials.length;
    }
  }

  // Adjust testimonialsToShow on the client
  onMount(() => {
    const updateTestimonialsToShow = () => {
      testimonialsToShow = window.innerWidth <= 768 ? 1 : 3;
    };

    updateTestimonialsToShow(); // Set initial value
    window.addEventListener("resize", updateTestimonialsToShow);

    // Cleanup the event listener on component destroy
    return () => {
      window.removeEventListener("resize", updateTestimonialsToShow);
    };
  });
</script>

<svelte:head>
  <link
    rel="stylesheet"
    href="https://unpkg.com/mono-icons@1.0.5/iconfont/icons.css"
  />
</svelte:head>

<div class="flex flex-col gap-3 md:mt-32 sm:mt-[100px] mt-12">
  <h4
    class="text-[#262626] text-center md:text-[48px] sm:text-[38px] text-[28px] font-bold"
  >
    Our Testimonials
  </h4>

  <p
    class="text-[#333333] text-center md:text-[18px] sm:text-[16px] text-[14px] font-medium w-[80%] mx-auto"
  >
    Our satisfied clients share their success stories and experiences on their
    journey to better health and well-being.
  </p>
</div>

<div
  class="flex flex-row justify-center md:mt-20 mt-12 gap-x-8 {horizontalSectionMarginClass}"
>
  {#each testimonials.slice(currentIndex, currentIndex + testimonialsToShow) as testimonial}
    <div
      class="flex h-full flex-col rounded-2xl overflow-hidden group transition transform hover:scale-105 hover:shadow-lg"
    >
      <!-- Top Section -->
      <div
        class="flex flex-col md:gap-[50px] gap-10 bg-[#FAFDF5] md:p-11 sm:p-8 p-6 rounded-t-2xl transition-colors duration-300 group-hover:bg-[#D6F5A1]"
      >
        <img
          src="testimonials/quote.png"
          alt="quote icon"
          class="md:w-10 md:h-10 w-8 h-8 group-hover:scale-110 transition-transform duration-300"
        />
        <p
          class="font-medium md:text-[18px] sm:text-[16px] text-[14px] text-[#444444] group-hover:text-[#1F1F1F] transition-colors duration-300"
        >
          {testimonial.text}
        </p>
      </div>

      <!-- Bottom Section -->
      <div
        class="flex items-center gap-3 bg-[#E6F4D7] md:py-8 md:px-5 sm:py-5 sm:px-8 py-5 px-6 rounded-b-2xl transition-colors duration-300 group-hover:bg-[#AEE06C]"
      >
        <img
          src={testimonial.image}
          alt=""
          class="rounded-lg
          md:min-h-[60px] md:max-h-[60px] md:min-w-[60px] md:max-w-[60px]
          sm:min-h-[50px] sm:max-h-[50px] sm:min-w-[50px] sm:max-w-[50px]
          min-h-[40px] max-h-[40px] min-w-[40px] max-w-[40px]
          group-hover:scale-110 transition-transform duration-300"
        />
        <p
          class="font-semibold md:text-[18px] text-[16px] text-[#333333] group-hover:text-[#1A1A1A] transition-colors duration-300"
        >
          {testimonial.name}
        </p>
      </div>
    </div>
  {/each}
</div>

<div class="flex flex-row mt-10 gap-x-4 items-center justify-center">
  <button
    on:click={goLeft}
    class="flex justify-center items-center"
    aria-label="left-arrow-button"
  >
    <i class="mi mi-arrow-left"><span class="u-sr-only"></span></i>
  </button>

  <div class="flex flex- gap-2">
    {#each Array(Math.ceil(testimonials.length / testimonialsToShow)) as _, i}
      <span
        class="w-2.5 h-2.5 rounded-full inline-block"
        style="background-color: {i ===
        Math.floor(currentIndex / testimonialsToShow)
          ? '#356554'
          : '#E5F5BD'}"
      ></span>
    {/each}
  </div>

  <button on:click={goRight} class="" aria-label="right-arrow-button">
    <i class="mi mi-arrow-right"><span class="u-sr-only"></span></i>
  </button>
</div>

<style>
  .mi {
    font-size: 2rem;
  }
</style>
