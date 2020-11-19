<template>
  <div>
    <transition name="modal">
      <div v-if="isOpen">
        <div class="overlay" @click.self="isOpen = false">
          <div class="modal">
            <h1>{{ res.name.first }} {{ res.name.last }}</h1>
            <div>Age: {{ res.age }}</div>
            <br />
            <p>{{ res.about }}</p>
          </div>
        </div>
      </div>
    </transition>
    <button @click="isOpen = !isOpen">
      {{ isOpen ? "Quit" : "More Info" }}
    </button>
  </div>
</template>

<script>
export default {
  props: ["res"],
  data: function () {
    return {
      isOpen: false,
    };
  },
};
</script>

<style scoped>
.modal {
  width: 500px;
  margin: 0px auto;
  padding: 20px;
  background-color: #fff;
  border-radius: 2px;
  box-shadow: 0 2px 8px 3px;
  transition: all 0.2s ease-in;
  font-family: Helvetica, Arial, sans-serif;
}
.fadeIn-enter {
  opacity: 0;
}

.fadeIn-leave-active {
  opacity: 0;
  transition: all 0.2s step-end;
}

.fadeIn-enter .modal,
.fadeIn-leave-active.modal {
  transform: scale(1.1);
}
button {
  color: white;
  cursor: pointer;
  color: #4aae9b;
  border: 1px solid #4aae9b;
  border-radius: 2px;
  font-size: 1rem;
  padding: 2px;
}

.overlay {
  position: fixed;
  top: 0;
  left: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100%;
  background: #00000094;
  z-index: 999;
  transition: opacity 0.2s ease;
}
</style>