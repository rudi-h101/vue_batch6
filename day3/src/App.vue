<template>
  <div id="app">
    <ListData :listTodo="listTodo" />
    <InputText v-model="newTodo" />
    <ButtonDefault title="Tambahkan" :handlerClick="addTodo" />
    <div v-if="checkLen">Hebat!</div>
  </div>
</template>

<script>
import ListData from "@/components/ListData.vue";
import InputText from "@/components/forms/InputText.vue";
import ButtonDefault from "@/components/forms/ButtonDefault.vue";

export default {
  name: "App",
  components: {
    ListData,
    InputText,
    ButtonDefault,
  },
  data() {
    return {
      newTodo: "",
      listTodo: [],
    };
  },
  methods: {
    addTodo() {
      const currentText = this.newTodo.trim();
      if (currentText.length > 0) {
        this.listTodo.push(currentText);
        this.newTodo = "";
      }
    },
  },
  computed: {
    checkLen() {
      return this.listTodo.length >= 4;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
</style>
