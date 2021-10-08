<template>
  <div
    class="header lg:px-12 px-6 bg-gradient-to-b from-black to-transparent ov"
  >
    <nav class="flex flex-nowrap items-center h-16 pt-3 text-sm font-medium">
      <router-link to="/" class="mr-6">
        <img src="@/assets/guessflix.png" alt="Netflixlogo" class="w-24" />
      </router-link>
      <ul class="hidden md:gap-5 gap-2 ml-6 md:flex font-normal">
        <li>
          <router-link to="/"> Home </router-link>
        </li>
        <li>
          <router-link to="/quiz"> Quiz </router-link>
        </li>
        <li>
          <router-link to="/about"> About </router-link>
        </li>
        <li>
          <router-link to="/developers"> Developers </router-link>
        </li>
      </ul>

      <div class="dropdown inline-block relative md:hidden">
        <button
          class="
            text-white
            font-semibold
            py-2
            px-4
            rounded
            inline-flex
            items-center
          "
        >
          <span class="mr-1">Browse</span>
          <svg
            class="fill-current h-4 w-4"
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 20 20"
          >
            <path
              d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z"
            />
          </svg>
        </button>
        <ul class="dropdown-menu absolute hidden bg-black bg-opacity-40 pt-1">
          <li class="">
            <router-link
              class="
                rounded-t
                bg-black bg-opacity-40
                hover:bg-white hover:bg-opacity-10
                py-2
                px-4
                block
                whitespace-no-wrap
              "
              to="/"
              >Home</router-link
            >
          </li>
          <li class="">
            <router-link
              class="
                bg-black bg-opacity-40
                hover:bg-white hover:bg-opacity-10
                py-2
                px-4
                block
                whitespace-no-wrap
              "
              to="/quiz"
              >Quiz</router-link
            >
          </li>
          <li class="">
            <router-link
              class="
                rounded-b
                bg-black bg-opacity-40
                hover:bg-white hover:bg-opacity-10
                py-2
                px-4
                block
                whitespace-no-wrap
              "
              to="/about"
              >About</router-link
            >
          </li>
          <li class="">
            <router-link
              class="
                rounded-b
                bg-black bg-opacity-40
                hover:bg-white hover:bg-opacity-10
                py-2
                px-4
                block
                whitespace-no-wrap
              "
              to="/developers"
              >Developers</router-link
            >
          </li>
        </ul>
      </div>

      <router-link to="/quiz" class="ml-auto"
        ><Button title="Play Quiz" icon="fa fa-star" type="btn-red" />
      </router-link>
    </nav>
  </div>
</template>

<script>
import Button from "./Button.vue";
export default {
  name: "Header",
  props: {
    msg: String,
  },

  components: {
    Button,
  },
};
</script>

<style scoped>
nav {
  position: relative;
  z-index: 10;
}

ul li {
  color: #e5e5e5;
  transition: all 350ms ease;
}
li:active {
  font-weight: 900;
}

li:hover {
  color: #b3b3b3;
}

.dropdown:hover .dropdown-menu {
  display: block;
}

.header {
  position: absolute;
  top: 0;
  width: 100%;
  z-index: 99;
}
</style>
