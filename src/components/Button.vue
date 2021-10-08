<template>
  <button :class="type"><i :class="icon"></i> {{ title }}</button>
</template>

<script>
export default {
  name: "Button",
  props: {
    title: String,
    icon: String,
    type: String,
  },
};
</script>

<style scoped>
.btn-red {
  display: flex;
  background-color: #d81f26;
  padding: 0.5rem 1rem 0.5rem 1rem;
  border-radius: 4px;
  gap: 0.75rem;
  flex-direction: row;
  flex-wrap: nowrap;
  align-content: center;
  align-items: center;
  justify-content: center;
  font-weight: 500;
  opacity: 1;
  transition: opacity 250ms ease;
}

@media only screen and (max-width: 767px) {
  .btn-red {
    display: none;
  }
}

.btn-white {
  display: flex;
  background-color: white;
  color: black;
  padding: 0.8em 2.5em 0.8em 2.5em;
  border-radius: 4px;
  font-size: 1.2em;
  gap: 0.75em;
  flex-direction: row;
  flex-wrap: nowrap;
  align-content: center;
  align-items: center;
  justify-content: center;
  font-weight: 600;
  opacity: 1;
  transition: opacity 250ms ease;
}

.btn-info {
  display: flex;
  background-color: rgba(109, 109, 110, 0.7);
  color: white;
  padding: 0.8em 2.5em 0.8em 2.5em;
  border-radius: 4px;
  font-size: 1.2em;
  gap: 0.75em;
  flex-direction: row;
  flex-wrap: nowrap;
  align-content: center;
  align-items: center;
  justify-content: center;
  font-weight: 600;
  opacity: 1;
  transition: opacity 250ms ease;
}

@media only screen and (max-width: 767px) {
  .btn-info,
  .btn-white {
    font-size: 1em;
    padding: 0.8em 1em 0.8em 1em;
    width: 100%;
  }
}

button {
  cursor: pointer;
}

button:hover {
  opacity: 0.5;
}
</style>
