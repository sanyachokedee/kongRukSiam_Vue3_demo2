<template>
  <Card>
    <template v-slot:card-header>
      <h1>{{ name }}</h1>
      <p>เงินเดือน {{ salary }} บาท , ตำแหน่งงาน : {{ department }} เพศ {{ gender }} ทักษะ {{ language }}</p>
    </template>
    <template v-slot:card-button>
      <button @click="showDescription(id)">ดูรายละเอียด</button>&nbsp;
      <button @click="deleteEmployee(id)">ลบข้อมูล</button>
    </template>
    <template v-slot:card-content>
      <transition name="fade">
        <div v-show="isVisible">
          <p>เงินเดือน {{ salary }} บาท , ตำแหน่งงาน : {{ department }} {{gender}} {{language}}</p>
        </div>
      </transition>
    </template>
  </Card>
</template>
<script>
import Card from "./Card.vue";

export default {
  name: "Person",
  components: {
    Card,
  },

  data() {
    return {
      message: "ข้อมูลพนักงาน",
    };
  },
  props: {
    id: {
      type: Number,
    },
    name: {
      type: String,
      require: true,
    },
    salary: {
      type: Number,
      default: 100,
    },
    department: {
      type: String,
      required: true,
    },
    isVisible: {
      type: Boolean,
    },
    gender: {},
    language: {}
  },
  methods: {
    showDescription(id) {
      // console.log("show1 : " + id)
      this.$emit("show", id);
    },
    deleteEmployee(id) {
      // console.log("delete :" + id);
      this.$emit("deleteEmployee_pr", id);
    },
  },
};
</script>
<style scoped>
button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #ff0077;
  background: #ff0077;
  color: white;
  padding: 0.05rem 1rem;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
}
.fade-enter-from {
  opacity: 0;
}
.fade-enter-active {
  transition: all 0.5s linear;
}
</style>
