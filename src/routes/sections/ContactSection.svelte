<script>
  import SocialIcons from '@rodneylab/svelte-social-icons';
</script>

<section class="bg-[#f5fdf3] mt-20 py-12">
  <div class="max-w-6xl mx-auto px-4 text-center">
    <h2 class="text-3xl font-bold text-[#2f4f3f] mb-6">Book a Consultation with Me</h2>
    <p class="text-lg text-[#4a6e60] mb-8">
      Reach out to schedule a consultation now via Instagram or email!
    </p>

    <div class="flex justify-center gap-10">
      <!-- Instagram Button -->
      <a href="https://www.instagram.com/toobanutrition.co/" target="_blank" class="flex items-center gap-3 text-[#ffffff] bg-gradient-to-r from-[#8abf85] to-[#5f9e5b] px-6 py-3 rounded-xl hover:bg-gradient-to-l transition-colors duration-300">        
        <SocialIcons network="instagram" alt="" bgColor="#f5fdf3" fgColor="#C13584"/>     
        <span class="text-xl">Instagram</span>
      </a>

      <!-- Email Button -->
      <a href="mailto:toobaasif167@gmail.com" class="flex items-center gap-3 text-[#ffffff] bg-gradient-to-r from-[#6ba574] to-[#4b7d3c] px-6 py-3 rounded-xl hover:bg-gradient-to-l transition-colors duration-300">
        <SocialIcons network="email" alt="" bgColor="#f5fdf3" fgColor="#FFA500"/>     
        <span class="text-xl">Email</span>
      </a>
    </div>
  </div>
</section>
