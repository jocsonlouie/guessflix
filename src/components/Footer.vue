<template>
  <!--Footer-->

  <footer
    class="
      bg-black
      p-5
      flex flex-col
      text-center
      align-middle
      justify-center
      w-screen
    "
  >
    <div>
      <button
        class="
          bg-white
          text-blue-600
          shadow-lg
          font-normal
          h-10
          w-10
          items-center
          justify-center
          align-center
          rounded-full
          outline-none
          focus:outline-none
          p-3
        "
        type="button"
      >
        <i class="flex fab fa-twitter text-red-500"></i>
      </button>
      <button
        class="
          bg-white
          text-blue-600
          shadow-lg
          font-normal
          h-10
          w-10
          items-center
          justify-center
          align-center
          rounded-full
          outline-none
          focus:outline-none
          mx-3
          p-3
        "
        type="button"
      >
        <i class="flex fab fa-facebook-square text-red-500"></i></button
      ><button
        class="
          bg-white
          text-pink-400
          shadow-lg
          font-normal
          h-10
          w-10
          items-center
          justify-center
          align-center
          rounded-full
          outline-none
          focus:outline-none
          p-3
        "
        type="button"
      >
        <i class="flex fab fa-linkedin text-red-500"></i>
      </button>
    </div>
    <div class="py-5 mx-auto text-white">
      <ul class="hidden md:gap-2 gap-1 ml-6 md:flex font-small">
        <li>
          <router-link to="/"> Home |</router-link>
        </li>
        <li>
          <router-link to="/quiz">Quiz |</router-link>
        </li>
        <li>
          <router-link to="/about">About |</router-link>
        </li>
        <li>
          <router-link to="/developers"> Developers </router-link>
        </li>
      </ul>
    </div>
    <div>&copy; 2021 GuessFlix Inc. All Rights Reserved.</div>
  </footer>
</template>

<script>
export default {};
</script>

<style></style>
