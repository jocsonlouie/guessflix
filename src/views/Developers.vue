<template>
  <div class="pt-20 flex lg:px-12 px-6 flex-col justify-center">
    <div class="grid-container">
      <div
        class="
          developers
          bg-black
          flex
          items-center
          justify-center
          lg:text-5xl
          md:text-4xl
          uppercase
          font-medium
        "
      >
        <span class="">
          Developer <small class="text-xl italic"> Edition</small></span
        >
      </div>
      <div
        class="
          bts
          bg-black
          flex
          items-center
          justify-center
          lg:text-5xl
          md:text-4xl
          uppercase
          font-medium
        "
      >
        Behind the Scenes
      </div>
      <div
        class="
          guessflix
          bg-black
          flex
          items-center
          justify-center
          lg:text-5xl
          md:text-4xl
          uppercase
          font-medium
        "
      >
        Guessflix
      </div>
    </div>

    <h1 class="mt-10 text-2xl font-bold md-text center">Meet the Developers</h1>
    <div
      class="
        flex-container flex
        2xl:flex-nowrap
        flex-wrap
        gap-20
        mt-3
        overflow-y-hidden overflow-x-scroll
      "
    >
      <div
        class="
          flex-item flex
          justify-center
          items-center
          lg:ml-20
          md:ml-16
          ml-10
          md:grid-cols-2
        "
      >
        <span class="num">1</span
        ><img
          src="@/assets/luwi.jpg"
          alt=""
          class="w-full h-full rounded bg-white"
        />
      </div>
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
        <span class="num">2</span
        ><img
          src="https://i.ibb.co/wYh3w1J/tin.png"
          alt=""
          class="w-full h-full rounded bg-white"
        />
      </div>
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
        <span class="num">3</span
        ><img
          src="https://tip.instructure.com/files/5112820/download?download_frd=1&verifier=ihOhMXts4yqYF2RahDLQ42WvHTDvNpO9Eq8BHMOh"
          alt=""
          class="w-full h-full rounded bg-white"
        />
      </div>
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
        <span class="num">4</span
        ><img
          src="@/assets/redd.png"
          alt=""
          class="w-full h-full rounded bg-white"
        />
      </div>
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
        <span class="num">5</span
        ><img
          src="https://i.ibb.co/ZcwgTbw/erry.jpg"
          alt=""
          class="w-full h-full rounded bg-white"
        />
      </div>
    </div>
    <h1 class="mt-10 text-2xl font-bold">Tech Stack</h1>
    <div
      class="
        flex-container flex
        2xl:flex-nowrap
        flex-wrap
        gap-20
        mt-3
        overflow-y-hidden overflow-x-scroll
        mb-10
      "
    >
      <div
        class="
          flex-item flex
          justify-center
          items-center
          lg:ml-20
          md:ml-16
          ml-10
        "
      >
        <span class="num">0</span
        ><img
          src="@/assets/vue-pic.png"
          alt=""
          class="w-full h-full object-cover rounded bg-white"
        />
      </div>
      <div
        class="
          flex-item flex
          justify-center
          items-center
          lg:ml-10
          md:ml-16
          ml-10
        "
      >
        <span class="num">1</span>
        <img
          src="@/assets/tailwind-pic.png"
          alt=""
          class="w-full h-full object-cover rounded bg-white"
        />
      </div>
      <div
        class="
          flex-item flex
          justify-center
          items-center
          lg:ml-10
          md:ml-16
          ml-10
        "
      >
        <span class="num">2</span>
        <img
          src="@/assets/opentrivia-pic.png"
          alt=""
          class="w-full h-full object-cover rounded bg-white"
        />
      </div>
      <div
        class="
          flex-item flex
          justify-center
          items-center
          lg:ml-10
          md:ml-16
          ml-10
        "
      >
        <span class="num">3</span
        ><img
          src="@/assets/unsplash-pic.png"
          alt=""
          class="w-full h-full rounded object-cover bg-white"
        />
      </div>
      <div
        class="
          flex-item flex
          justify-center
          items-center
          lg:ml-10
          md:ml-16
          ml-10
        "
      >
        <span class="num">4</span
        ><img
          src="@/assets/js-cookie-pic.png"
          alt=""
          class="w-full h-full ite"
        />
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Developers",
};
</script>

<style scoped>
.grid-container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 1fr 1fr;
  gap: 0px 0px;
  grid-auto-flow: row;
  grid-template-areas:
    "bts developers"
    "guessflix developers";
  min-height: 50vh;
  gap: 0.8rem;
  align-content: stretch;
  align-items: stretch;
  justify-items: stretch;
  justify-content: center;
}

.grid-container div,
.grid-container span {
  border-radius: 0.375rem;
  font-family: "Bebas Neue", cursive;
}

.developers {
  grid-area: developers;
  background: linear-gradient(0deg, rgba(0, 0, 0, 0.87), rgba(0, 0, 0, 0.657)),
    url("https://images.unsplash.com/photo-1580894742597-87bc8789db3d?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1170&q=80")
      no-repeat center center;
  background-size: cover;
  background-blend-mode: screen multiply;
}

.bts {
  grid-area: bts;
  background: linear-gradient(0deg, rgba(0, 0, 0, 0.87), rgba(0, 0, 0, 0.657)),
    url("https://images.unsplash.com/photo-1600258731336-c6ea9eba3064?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1632&q=80")
      no-repeat top center;
  background-size: cover;
  background-blend-mode: screen multiply;
}

.guessflix {
  grid-area: guessflix;
  background: linear-gradient(0deg, rgba(0, 0, 0, 0.87), rgba(0, 0, 0, 0.657)),
    url("https://static.highsnobiety.com/thumbor/RY6YRno8Vgpb89fV5-7gSMk0dyc=/1600x1067/static.highsnobiety.com/wp-content/uploads/2018/05/16153017/netflix-recommendations-main5.jpg")
      no-repeat top center;
  background-size: cover;
  background-blend-mode: screen multiply;
}

.flex-container::-webkit-scrollbar {
  display: none;
}

.flex-item {
  width: 220px;
  height: 220px;
}

@media only screen and (max-width: 767px) {
  .flex-item {
    width: 450px;
    height: 350px;
  }
}

.flex-item img {
  position: relative;
  z-index: 1;
  margin-left: -1.5rem;
}

.num {
  font-size: 12rem;
  font-weight: 600;
  color: black;
  -webkit-text-stroke-width: 5px;
  -webkit-text-stroke-color: #595959;
  transform: scale(1.4);
}
</style>
