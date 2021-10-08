<template>
  <div class="overflow-x-hidden">
    <Loader v-if="quizLoader" />
    <div
      class="
        quiz-screen
        h-screen
        bg-gray-600
        md:px-12
        px-6
        flex flex-col
        justify-center
      "
    >
      <transition name="fade">
        <!-- START LAYOUT -->

        <div
          class="
            absolute
            bg-black bg-opacity-60
            p-3
            inset-0
            z-50
            text-white
            flex flex-col
            justify-center
            items-center
          "
          v-if="quizStart"
        >
          <div
            class="
              flex flex-col
              justify-center
              items-center
              p-10
              custom-design-modal
            "
          >
            <div class="header-title2 lg:text-6xl md:text-3xl mx-auto">
              GUESSFLIX
              <span class="header-title1 lg:text-4xl md:text-2xl"
                >ORIGINAL</span
              >
            </div>
            <div
              class="
                header-title3
                md:text-7xl
                text-12xl
                mx-auto
                text-transparent
                bg-clip-text bg-gradient-to-t
                from-red-800
                via-red-500
                to-red-800
              "
            >
              TRIVIA QUIZ
            </div>
            <div
              class="
                flex
                md:gap-4
                gap-2
                md:text-2xl
                text-xl
                md:mt-5
                mt-3
                mx-auto
              "
            >
              <div class="text-yellow-300">★★★★★</div>
              <div>2021</div>
              <div>10 Questions</div>
              <div>Your Highest Score: {{ highestscore }}</div>
            </div>
            <Button
              title="START QUIZ"
              icon="fas fa-play"
              type="btn-white md:mt-5 mt-3 "
              @click="fetchQuestionsFromServer"
            />
          </div>
        </div>
      </transition>
      <transition class="fade">
        <QuizEnd
          v-if="certificateModal"
          @click="certificateModal = !certificateModal"
        />
      </transition>

      <div class="flex justify-center items-center pt-24 md:pt-0">
        <div
          class="relative modal-main max-w-5xl w-full h-full overflow-hidden"
        >
          <div class="max-w-5xl">
            <div
              style="flex-basis: 50%"
              class="
                relative
                flex
                justify-center
                items-center
                text-3xl
                font-semibold
                gap-4
                w-full
                mb-5
                md:flex-nowrap
                flex-wrap
              "
            >
              <!-- <div class="absolute z-10 inset-0 gradient-to-top"></div> -->
              <div
                class="
                  custom-design
                  md:w-4/12
                  w-1/2
                  flex flex-col
                  justify-center
                  items-center
                  md:order-1
                  order-2
                "
              >
                <h3
                  class="
                    relative
                    text-white
                    z-20
                    md:text-lg
                    text-sm
                    font-normal
                    uppercase
                  "
                >
                  DIFFICULTY
                </h3>
                <h2
                  class="relative text-white z-20 md:text-3xl text-lg uppercase"
                >
                  {{ currentQuestion.difficulty }}
                </h2>
              </div>
              <div
                class="
                  custom-design
                  md:w-8/12
                  flex flex-col
                  justify-center
                  items-center
                  md:order-2
                  order-1
                "
              >
                <div class="header-title2 md:text-2xl text-base text-white">
                  GUESSFLIX
                  <span class="header-title1 md:text-2xl text-base text-white"
                    >ORIGINAL</span
                  >
                </div>
                <div
                  class="
                    header-title3
                    md:text-6xl
                    text-3xl text-transparent
                    bg-clip-text bg-gradient-to-t
                    from-red-800
                    via-red-500
                    to-red-800
                  "
                >
                  TRIVIA QUIZ
                </div>
              </div>
              <div
                class="
                  custom-design
                  md:w-2/6
                  w-1/3
                  flex flex-col
                  justify-center
                  items-center
                  md:order-3
                  order-3
                "
              >
                <h3
                  class="relative text-white z-20 md:text-lg text-sm uppercase"
                >
                  score
                </h3>
                <h2
                  class="relative text-white z-20 md:text-3xl text-lg uppercase"
                >
                  {{ score }}/100
                </h2>
              </div>
            </div>
            <div
              v-if="!endOfQuiz"
              class="
                relative
                w-full
                h-3
                round
                overflow-hidden
                bg-white
                mb-5
                rounded
              "
            >
              <div
                class="
                  absolute
                  h-3
                  transition-all
                  duration-150
                  ease-in
                  bg-red-600
                "
                :style="`width:${timer}%`"
              ></div>
            </div>
            <div
              class="
                md:px-12
                px-6
                pt-8
                py-6
                black-bg
                flex
                justify-center
                items-center
              "
              v-if="endOfQuiz"
            >
              <div v-if="score >= 30" class="w-full max-w-2xl">
                <h2 class="text-4xl mt-5 text-white text-center font-bold">
                  Congratulations!🎉
                </h2>
                <h2 class="text-base mt-2 text-white text-center">
                  What a true Film master! Here's your certificate as promise!
                </h2>
                <div class="flex md:gap-5 gap-3">
                  <a href="/quiz" class="w-1/2">
                    <Button
                      title="Play Again"
                      icon="fas fa-play"
                      type="btn-info md:mt-5 mt-3 w-full"
                    />
                  </a>
                  <Button
                    @click="certificateModal = !certificateModal"
                    title="View Certificate"
                    icon="fas fa-certificate"
                    type="btn-white md:mt-5 mt-3 "
                    class="w-1/2"
                  />
                </div>
              </div>
              <div v-if="score < 30">
                <h2 class="text-4xl mt-5 text-white text-center font-bold">
                  Nice try!
                </h2>
                <h2 class="text-base mt-2 text-white text-center">
                  Click the button below to seek revenge!
                </h2>
                <div class="flex md:gap-5 gap-3">
                  <a href="/quiz" class="w-full">
                    <Button
                      title="Try Again"
                      icon="fas fa-play"
                      type="btn-info md:mt-5 mt-3 w-full"
                    />
                  </a>
                </div>
              </div>
            </div>
            <div class="md:px-12 px-6 pt-8 py-6 black-bg" v-else>
              <h2
                class="md:text-4xl text-2xl text-white font-bold"
                v-html="currentQuestion.question"
              ></h2>
              <div class="grid-choices mt-5">
                <div
                  class="
                    grid-items
                    px-5
                    flex flex-col-reverse
                    text-center
                    gap-2
                    md:flex-row
                    md:gap-4
                    uppercase
                    font-semibold
                    justify-center
                    items-center
                    cursor-pointer
                    rounded
                    text-white
                    bg-white bg-opacity-50
                    opacity-100
                    hover:opacity-50
                    transition-opacity
                  "
                  :data-key="item"
                  v-for="(choice, item) in currentQuestion.choices"
                  :key="item"
                  :ref="optionChosen"
                  @click="onOptionClicked(choice, item)"
                  :v-html="choice"
                >
                  {{ choice }}
                  <i class="fas fa-medal hidden"></i>
                  <i class="fas fa-heart-broken hidden"></i>
                </div>
              </div>
              <div class="text-white text-center font-bold mt-5">
                {{ questionCounter }}/10
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from "@vue/reactivity";
import { onMounted } from "@vue/runtime-core";

import Button from "@/components/Button";
import QuizEnd from "@/components/QuizEnd";
import Loader from "@/components/Loader";

import axios from "axios";

// @ is an alias to /src

//import Button from "@/components/Button";
export default {
  name: "Quiz",
  setup() {
    // https://opentdb.com/api.php?amount=10&category=11&type=multiple
    let canClick = true;
    let quizStart = ref(true);
    let quizLoader = ref(false);
    let timer = ref(100);
    let endOfQuiz = ref(false);
    let questionCounter = ref(0);
    const STORAGE_KEY = "highscore";
    let highestscore = ref(localStorage.getItem(STORAGE_KEY));
    let score = ref(0);
    const currentQuestion = ref({
      question: "",
      answer: 1,
      choices: [],
      difficulty: "",
    });

    let questions = [];

    const loadQuestion = () => {
      canClick = true;
      if (questions.length > questionCounter.value) {
        //load
        console.log("" + questions.length + " " + questionCounter.value);
        timer.value = 100;
        currentQuestion.value = questions[questionCounter.value];
        console.log("current ques", currentQuestion.value);
        questionCounter.value++;
      } else {
        endOfQuiz.value = true;
        checkScore();
      }
    };

    // methods
    let itemsRef = [];
    const optionChosen = (element) => {
      if (element) {
        itemsRef.push(element);
      }
    };

    const clearSelected = (divSelected) => {
      setTimeout(() => {
        divSelected.classList.remove("option-correct");
        divSelected.classList.remove("option-wrong");
        loadQuestion();
      }, 1500);
    };

    const onOptionClicked = (choice, item) => {
      if (canClick) {
        const divContainer = itemsRef[item];
        const optionID = item + 1;
        if (currentQuestion.value.answer == optionID) {
          console.log("You are correct bitch!");
          score.value += 10;
          divContainer.classList.add("option-correct");
        } else {
          console.log("You are wrong bitch!");
          divContainer.classList.add("option-wrong");
        }
        timer.value = 100;
        canClick = false;

        // go to next ques
        clearSelected(divContainer);
        console.log(choice, item);
      } else {
        console.log("cant select");
      }
    };

    const countDownTimer = function () {
      let interVal = setInterval(() => {
        if (timer.value > 0) {
          timer.value--;
        } else {
          if (questionCounter > 10) {
            endOfQuiz.value = true;
          } else {
            loadQuestion();
            countDownTimer();
            clearInterval(interVal);
          }
        }
      }, 100);
    };

    const checkScore = function () {
      if (score.value > parseInt(localStorage.getItem(STORAGE_KEY))) {
        localStorage.setItem(STORAGE_KEY, score.value);
      } else {
        console.log("error daffuk");
      }
    };

    const fetchQuestionsFromServer = async function () {
      quizStart.value = false;
      quizLoader.value = true;
      try {
        // loader.value = false;
        const response = await axios.get(
          "https://opentdb.com/api.php?amount=10&category=11&type=multiple"
        );
        // const data = await response.json();
        const newQuestions = response.data.results.map((serverQuestions) => {
          const arrangedQuestion = {
            question: serverQuestions.question,
            choices: "",
            answer: "",
            difficulty: serverQuestions.difficulty,
          };

          const choices = serverQuestions.incorrect_answers;

          arrangedQuestion.answer = Math.floor(Math.random() * 4 + 1);

          choices.splice(
            arrangedQuestion.answer - 1,
            0,
            serverQuestions.correct_answer
          );
          arrangedQuestion.choices = choices;

          return arrangedQuestion;
        });

        // loader.value = false;

        console.log("ew what", newQuestions);

        questions = newQuestions;
        console.log("new formatted ques", questions);
        loadQuestion();
        countDownTimer();
        quizLoader.value = false;
      } catch (e) {
        console.error(e);
      }
    };

    onMounted(() => {
      // fetchQuestionsFromServer();
      console.log(localStorage.getItem(STORAGE_KEY));
      if (localStorage.getItem(STORAGE_KEY) == null) {
        localStorage.setItem(STORAGE_KEY, "0");
      } else {
        console.log(localStorage.getItem(STORAGE_KEY));
      }
    });

    return {
      quizStart,
      quizLoader,
      fetchQuestionsFromServer,
      timer,
      currentQuestion,
      questions,
      score,
      questionCounter,
      loadQuestion,
      onOptionClicked,
      optionChosen,
      endOfQuiz,
      highestscore,
    };
  },
  components: {
    Button,
    QuizEnd,
    Loader,
  },
  data() {
    return {
      certificateModal: false,
      spin: false,
    };
  },
};
</script>

<style scoped>
.wrapper {
  width: 100%;
}

.custom-design {
  background-image: url("data:image/svg+xml,%3csvg width='100%25' height='100%25' xmlns='http://www.w3.org/2000/svg'%3e%3crect width='100%25' height='100%25' fill='none' stroke='white' stroke-width='12' stroke-dasharray='2%2c 6' stroke-dashoffset='28' stroke-linecap='butt'/%3e%3c/svg%3e");
  padding: 1em;
  background-color: rgba(0, 0, 0, 0.2);
  backdrop-filter: blur(10px);
}

.custom-design-modal {
  background-image: url("data:image/svg+xml,%3csvg width='100%25' height='100%25' xmlns='http://www.w3.org/2000/svg'%3e%3crect width='100%25' height='100%25' fill='none' stroke='white' stroke-width='12' stroke-dasharray='2%2c 6' stroke-dashoffset='28' stroke-linecap='butt'/%3e%3c/svg%3e");
  background-color: rgba(0, 0, 0, 0.1);
  backdrop-filter: blur(10px);
}

.quiz-screen {
  background: linear-gradient(
      to bottom,
      rgba(0, 0, 0, 0.52),
      rgba(0, 0, 0, 0.73)
    ),
    url("https://static.highsnobiety.com/thumbor/RY6YRno8Vgpb89fV5-7gSMk0dyc=/1600x1067/static.highsnobiety.com/wp-content/uploads/2018/05/16153017/netflix-recommendations-main5.jpg")
      no-repeat top center fixed;
  /* https://i.imgur.com/Vo99rik.gif */
  background-size: cover;
  color: black;
}

.black-bg {
  background-color: #141414;
}

.gradient-to-top {
  background-image: linear-gradient(to top, #141414, transparent);
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

.header-title1 {
  font-family: "Nunito", sans-serif;
}

.header-title2 {
  font-family: "Ubuntu", sans-serif;
}

.header-title3 {
  width: auto;
  font-family: "Acme", sans-serif;
}

.text-12xl {
  font-size: 12vw;
}

.hero-img-top {
  background: url("https://source.unsplash.com/random/?film") no-repeat center
    center;
  background-size: cover;
  /* background-image: linear-gradient(to top, #141414, transparent); */
  width: 100%;
  height: 15.625rem;
}
</style>
