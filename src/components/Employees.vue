<template>
  <div>
    <div class="home">
      <div class="pict" v-bind:key="result.id" v-for="result in employees">
        <div class="employee">
          <img v-bind:src="result.picture" />
          <div>{{ result.name.first }} {{ result.name.last }}</div>
          <div>{{ result.phone }}</div>
          <div>{{ result.email }}</div>
          <Modal v-bind:res="result" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Modal from "../components/Modal";
export default {
  name: "Employees",
  components: {
    Modal,
  },
  props: ["employees"],
};
</script>

<style scoped>
.pict img {
  height: 100px;
  margin: 10px;
}
.home {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  margin-top: 30px;
}
.employee {
  display: flex;
  align-items: center;
  flex-direction: column;
  padding: 10px;
}
</style>