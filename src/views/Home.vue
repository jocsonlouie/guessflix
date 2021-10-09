<template>
  <div
    class="
      header-screen
      h-screen
      lg:px-12
      md:pt-0
      px-6
      pt-16
      flex flex-col
      justify-center
      overflow-x-hidden
    "
  >
    <div class="">
      <div class="header-title2 md:text-3xl text-lg">
        GUESSFLIX
        <span class="header-title1 md:text-2xl text-xl">ORIGINAL</span>
      </div>
      <div
        class="
          header-title3
          md:text-8xl
          text-7xl text-transparent
          bg-clip-text bg-gradient-to-t
          from-red-800
          via-red-500
          to-red-800
        "
      >
        TRIVIA QUIZ
      </div>

      <div class="flex md:gap-4 gap-2 md:text-2xl text-xl md:mt-5 mt-3">
        <div class="text-yellow-300">★★★★★</div>
        <div>2021</div>
        <div>10 Questions</div>
      </div>
      <p
        class="max-w-screen-sm md:text-2xl text-base md:mt-5 mt-3 text-justify"
      >
        Do you think you've watched all the films already? We don't think you
        do. Take this quiz that contains the easiest to difficult questions, and
        let us know what score you got! Take the challenge now by clicking the
        play button!
      </p>

      <div class="flex md:gap-5 gap-3">
        <router-link to="/quiz">
          <Button
            title="Play"
            icon="fas fa-play"
            type="btn-white md:mt-5 mt-3 "
          />
        </router-link>
        <Button
          @click="Modal = !Modal"
          title="More info"
          icon="far fa-question-circle"
          type="btn-info md:mt-5 mt-3 "
        />
      </div>
      <transition name="fade">
        <div v-if="Modal" transition="fade">
          <div class="absolute z-10 inset-0 opacity-50 bg-black"></div>
          <div
            class="
              fixed
              z-20
              overflow-x-hidden
              overscroll-y-auto
              inset-0
              flex
              md:justify-center
              md:items-center
              justify-start
              items-start
              md:mt-0
              mt-20
            "
          >
            <div
              class="
                relative
                modal-main
                mx-auto
                w-auto
                max-w-4xl
                overflow-hidden
              "
            >
              <i
                @click="Modal = !Modal"
                class="
                  fas
                  fa-times
                  absolute
                  z-30
                  right-0
                  pt-3
                  pr-3
                  text-2xl
                  cursor-pointer
                "
              ></i>
              <div class="black-bg">
                <div
                  class="
                    relative
                    flex
                    items-center
                    hero-img-top
                    md:px-12
                    px-6
                    py-6
                    text-3xl
                    font-semibold
                  "
                >
                  <div class="absolute z-10 inset-0 gradient-to-top"></div>
                  <div class="flex flex-col justify-center">
                    <h2 class="relative z-20 header-title1">
                      <span
                        class="text-red-600 md:text-6xl text-5xl header-title2"
                        >GUESSFLIX</span
                      >
                      ABOUT
                    </h2>
                  </div>
                </div>
                <div class="md:px-12 px-6 pb-12">
                  <h2 class="justify-center text-justify">
                    GuessFlix is a game that will test your limits in the
                    knowledge of Films. It is a quiz game wherein trivia from
                    different films is asked. The game is composed of 10
                    questions ranging from easy to hard difficulty. Each
                    question has four choices to select, and only one is
                    correct. Dare to seek the questions up ahead? Take the quiz
                    now! Measure the knowledge you hold in Films. Invite your
                    friends and compete with your scores!
                  </h2>
                </div>
                <div class="md:px-12 px-6 pb-12">
                  <h6 class="justify-center text-justify font-small">
                    To know about the game, click the button below.
                  </h6>
                  <div class="flex">
                    <router-link to="/about" class="md:w-4/12 w-full">
                      <Button
                        title="About"
                        type="btn-info mt-3 w-full "
                        icon="fas fa-dice-d20"
                      />
                    </router-link>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </transition>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Button from "@/components/Button";

export default {
  name: "Home",
  data() {
    return {
      toggleModal: false,
      Modal: false,
    };
  },
  components: {
    Button,
  },
};
</script>

<style scoped>
.header-screen {
  background: url("https://i.imgur.com/PzWACN1.jpg") no-repeat top center fixed;
  background-size: cover;
}

.header-title1 {
  font-family: "Nunito", sans-serif;
}

.header-title2 {
  font-family: "Ubuntu", sans-serif;
}

.header-title3 {
  width: auto;
  font-family: "Acme", sans-serif;
  /* position: relative;
    z-index: 50; */
}

/* .header-title3::before {
    content: '\f87c';
    position: absolute;
    font-weight: 600;
    z-index: 0;
    font-size: 3rem;
    color: white;
    font-family: "Font Awesome 6 Free";
    left: 26%;
    top: -20%;
    transform: rotate(10deg);
} */

.black-bg {
  background-color: #141414;
}

.modal-main {
  border-radius: 0.375rem;
}

.gradient-to-top {
  background-image: linear-gradient(to top, #141414, transparent);
}

.hero-img-top {
  background: url("https://source.unsplash.com/random/?film") no-repeat center
    center;
  background-size: cover;
  /* background-image: linear-gradient(to top, #141414, transparent); */
  width: 100%;
  height: 15.625rem;
}

.grid-choices {
  display: grid;
  grid-template-columns: 1fr 1fr;
  height: 120px;
  align-items: stretch;
  justify-items: stretch;
  gap: 0.5rem;
  align-content: stretch;
  justify-content: space-evenly;
}

/* 
.grid-items {
    border-radius: 0.25rem;
    padding: 0.8rem;
    background-color: rgba(109, 109, 110, 0.7);
    opacity: 1;
    transition: opacity 250ms ease;
    cursor: pointer;
}

.grid-items:hover{
    opacity: 0.5;
} */

.fade-transition {
  transition: all 1s ease;
  transform: scale(1);
}

/* .fade-enter defines the starting state for entering */
/* .fade-leave defines the ending state for leaving */
.fade-enter,
.fade-leave {
  scale: (0.5);
}
</style>
