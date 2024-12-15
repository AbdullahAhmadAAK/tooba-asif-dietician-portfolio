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

<div class="flex flex-col gap-3">
  <h4 class="text-[#262626] text-center text-[48px] font-bold">Features</h4>

  <p class="text-[#333333] text-center text-[18px] font-medium">
    Here are the different services I provide to help you achieve your health
    goals and embrace a healthier lifestyle.
  </p>
</div>

<div class="grid grid-cols-2 gap-8 mt-20 {horizontalSectionMarginClass}">
  {#each features as feature}
    <div
      class="bg-[#F6FBE9] flex flex-col gap-6 py-10 px-14 rounded-xl transition duration-300 hover:bg-[#D6F5A1] hover:shadow-lg hover:scale-105"
    >
      <div class="flex items-center gap-4">
        <div
          class="flex justify-center items-center bg-[#CBEA7B] rounded-lg w-[68px] h-[68px] transition duration-300 hover:bg-[#AEE06C]"
        >
          <img src={feature.image} alt="" class="w-10 h-10" />
        </div>
        <h5 class="text-[24px] font-semibold text-[#262626] transition duration-300 hover:text-[#1A1A1A]">
          {feature.title}
        </h5>
      </div>
      <p class="text-[18px] font-medium text-[#333333] transition duration-300 hover:text-[#1F1F1F]">
        {feature.description}
      </p>
    </div>
  {/each}
</div>

