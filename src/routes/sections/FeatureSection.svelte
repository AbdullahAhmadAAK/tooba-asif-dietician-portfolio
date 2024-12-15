<script>
  import {
    horizontalSectionPaddingClass,
    horizontalSectionMarginClass,
  } from "$lib/portfolio-details";

  const features = [
    {
      title: "Personalized Nutrition Plans",
      description:
        "Customized nutrition plans tailored to individual health goals, preferences, and lifestyle.",
      image: "features/Flower.png",
    },
    {
      title: "Weight Management Solutions",
      description:
        "Programs for effective weight loss or gain, including support for obesity management.",
      image: "features/WeightMachine.png",
    },
    {
      title: "Athlete Nutrition Coaching",
      description:
        "Optimized meal plans for fitness enthusiasts and athletes to enhance performance and recovery.",
      image: "features/Dumbell.png",
    },
    {
      title: "Illness-Specific Nutrition",
      description:
        "Dietary plans designed to complement treatment for chronic illnesses and promote recovery.",
      image: "features/Illness.png",
    },
    {
      title: "Meal Prep Guidance",
      description:
        "Practical advice on planning and preparing meals that align with dietary goals.",
      image: "features/Planner.png",
    },
    {
      title: "Nutritional Education and Workshops",
      description:
        "Interactive sessions to promote healthy eating habits and overall wellness.",
      image: "features/WorkshopBag.png",
    },
  ];
</script>

<div class="flex flex-col gap-3 md:mt-32 sm:mt-[100px] mt-12" id="services">
  <h4
    class="text-[#262626] text-center md:text-[48px] sm:text-[38px] text-[28px] font-bold"
  >
    Features
  </h4>

  <p
    class="text-[#333333] text-center md:text-[18px] sm:text-[16px] text-[14px] font-medium w-[80%] mx-auto"
  >
    Here are the different services I provide to help you achieve your health
    goals and embrace a healthier lifestyle.
  </p>
</div>

<div
  class="grid md:grid-cols-2 grid-cols-1 md:gap-8 gap-5 md:mt-20 sm:mt-15 mt-12 {horizontalSectionMarginClass}"
>
  {#each features as feature}
    <div
      class="bg-[#F6FBE9] flex group flex-col gap-6 md:py-10 md:px-14 sm:p-10 p-7 rounded-xl transition duration-300 hover:bg-[#D6F5A1] hover:shadow-lg hover:scale-105"
    >
      <div class="flex items-center md:gap-4 gap-[10px]">
        <div
          class="flex justify-center items-center bg-[#CBEA7B] rounded-lg md:min-w-[68px] md:min-h-[68px] sm:min-w-[54px] sm:min-h-[54px] min-w-[48px] min-h-[48px] transition duration-300 group-hover:bg-[#AEE06C]"
        >
          <img
            src={feature.image}
            alt=""
            class="md:w-10 md:h-10 sm:w-7 sm:h-7 w-6 h-6"
          />
        </div>
        <h5
          class="md:text-[24px] sm:text-[20px] text-[18px] font-semibold text-[#262626] transition duration-300 group-hover:text-[#1A1A1A]"
        >
          {feature.title}
        </h5>
      </div>
      <p
        class="md:text-[18px] sm:text-[16px] text-[14px] font-medium text-[#333333] transition duration-300 group-hover:text-[#1F1F1F]"
      >
        {feature.description}
      </p>
    </div>
  {/each}
</div>
