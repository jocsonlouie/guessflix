<template>
  <div class="overflow-x-hidden">
    <div class="flex flex-cols about-screen lg:p-64 md:p-52 p-28">
      <div class="mx-auto p-4 text-center bg-black bg-opacity-40">
        <h1 class="text-white font-semibold text-5xl">
          GUESSFLIX: A Trivia Quiz Game for International and Local Films
        </h1>
        <p class="mt-4 text-lg text-gray-300">
          We hope that you can still remember the good old days wherein we can
          still watch movies in our favorite movie theater. May this game help
          you remember your favorite movies by answering all of the provided
          questions. Enjoy!
        </p>
      </div>
    </div>
    <!--2nd portion -->
    <div class="container mx-auto px-4">
      <div class="items-center flex flex-wrap">
        <div
          class="
            flex-item flex
            justify-center
            items-center
            lg:ml-10
            md:ml-16
            ml-10
            md:grid-cols-2
          "
        >
          <span class="num lg:ml-20 md:ml-16 ml-10">G</span
          ><img
            src="https://i.ibb.co/XzQGCbs/netflix-image.jpg"
            alt=""
            class="w-full h-full rounded bg-white"
            style="max-width: 18rem"
          />
        </div>
        <div
          class="w-full md:w-5/12 ml-auto mr-auto px-4 my-10"
          data-aos="fade-left"
        >
          <div class="md:pr-12">
            <div
              class="
                p-3text-center
                inline-flex
                items-center
                justify-center
                w-16
                h-16mb-6
                shadow-lg
                rounded-full
                text-red-50
              "
            ></div>
            <h3 class="text-4xl text-center uppercase font-bold">
              Game Mechanics and Instructions
            </h3>
          </div>
          <p class="mt-4 text-lg leading-relaxed text-center">
            Excited to know how to play the game? It's easy as pie!
          </p>
          <ul class="list-none mt-6 text-center ml-5">
            <li class="py-2">
              <div class="flex items-center">
                <div>
                  <span
                    class="
                      text-xs
                      font-semibold
                      inline-block
                      py-3
                      mr-3
                      text-red-500 text-center
                    "
                    ><i class="fas fa-gamepad text-center"></i
                  ></span>
                </div>
                <div>
                  <h4 class="text-white-600">
                    The Trivia Quiz is about Film in Entertainment Industry
                  </h4>
                </div>
              </div>
            </li>
            <li class="py-2">
              <div class="flex items-center">
                <div>
                  <span
                    class="
                      text-xs
                      font-semibold
                      inline-block
                      py-3
                      mr-3
                      text-red-500
                    "
                    ><i class="fas fa-gamepad"></i
                  ></span>
                </div>
                <div>
                  <h4 class="text-white-600">
                    There are 10 questions to answer
                  </h4>
                </div>
              </div>
            </li>
            <li class="py-2">
              <div class="flex items-center">
                <div>
                  <span
                    class="
                      text-xs
                      font-semibold
                      inline-block
                      py-3
                      mr-3
                      text-red-500
                    "
                    ><i class="fas fa-clock"></i>
                  </span>
                </div>
                <div>
                  <h4 class="text-white-600">
                    Each question has a timer that is set for 20 seconds
                  </h4>
                </div>
              </div>
            </li>
            <li class="py-2">
              <div class="flex items-center">
                <div>
                  <span
                    class="
                      text-xs
                      font-semibold
                      inline-block
                      py-3
                      mr-3
                      text-red-500
                    "
                    ><i class="fas fa-clock"></i>
                  </span>
                </div>
                <div>
                  <h4 class="text-white-600">
                    There is only one correct answer from the four choices
                  </h4>
                </div>
              </div>
            </li>
            <li class="py-2">
              <div class="flex items-center">
                <div>
                  <span
                    class="
                      text-xs
                      font-semibold
                      inline-block
                      py-3
                      mr-3
                      text-red-500
                    "
                    ><i class="fas fa-trophy"></i>
                  </span>
                </div>
                <div>
                  <h4 class="text-white-600">That's it! You're good to go!</h4>
                </div>
              </div>
            </li>
          </ul>
        </div>
      </div>
    </div>
    <!-- end 2nd portion -->
    <h3 class="text-4xl text-center uppercase font-bold">Scoring System</h3>
    <div class="flex flex-wrap py-10">
      <div
        class="w-full md:w-6/12 lg:w-4/12 lg:mb-0 mb-12 px-4"
        data-aos="flip-right"
      >
        <div class="px-6">
          <h3
            class="
              text-4xl
              uppercase
              font-bold
              text-transparent
              bg-clip-text bg-gradient-to-t
              from-red-800
              via-red-500
              to-red-800
              text-center
            "
          >
            CONGRATULATIONS!
          </h3>
          <div class="pt-6 text-center">
            <h5 class="text-xl font-bold">30 and above</h5>
            <p class="mt-1 text-sm text-gray-300 uppercase font-semibold">
              Congratulations you will receive an award
            </p>
          </div>
        </div>
      </div>
      <div
        class="w-full md:w-4/12 lg:w-4/12 lg:mb-0 mb-12 px-4"
        data-aos="flip-right"
      >
        <div class="px-6">
          <h3
            class="
              text-4xl
              uppercase
              font-bold
              text-transparent
              bg-clip-text bg-gradient-to-t
              from-red-800
              via-red-500
              to-red-800
              text-center
            "
          >
            NICE TRY!
          </h3>
          <div class="pt-6 text-center">
            <h5 class="text-xl font-bold">Below 30</h5>
            <p class="mt-1 text-sm text-gray-300 uppercase font-semibold">
              Nice Try
            </p>
          </div>
        </div>
      </div>
      <div
        class="w-full md:w-4/12 lg:w-4/12 lg:mb-0 mb-12 px-4"
        data-aos="flip-right"
      >
        <div class="px-6">
          <h3
            class="
              text-4xl
              uppercase
              font-bold
              text-transparent
              bg-clip-text bg-gradient-to-t
              from-red-800
              via-red-500
              to-red-800
              text-center
            "
          >
            BETTER LUCK NEXT TIME!
          </h3>
          <div class="pt-6 text-center">
            <h5 class="text-xl font-bold">0</h5>
            <p class="mt-1 text-sm text-gray-300 uppercase font-semibold">
              Sorry Better Luck Next Time
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "About",
};
</script>

<style scoped>
.about-screen {
  background: url("https://t4.ftcdn.net/jpg/02/31/83/73/360_F_231837316_VEjVeR0CEJ8u4f0bLofm4BN8Fp8UpzHB.jpg")
    no-repeat top center fixed;
  background-size: cover;
}

.num {
  font-size: 18rem;
  font-weight: 600;
  color: black;
  -webkit-text-stroke-width: 5px;
  -webkit-text-stroke-color: #595959;
  transform: scale(1.4);
}
</style>
