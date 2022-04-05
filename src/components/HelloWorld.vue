<template>
  <div>
    <p>{{ count }}</p>
    <button class="tambah" @click="increment()">TAMBAH</button>
    <button class="kurang" @click="decrement()">KURANGI</button>
  </div>
</template>

<script>
import { computed } from "vue";
import { useStore } from "vuex";

export default {
  setup() {
    const store = useStore();
    const count = computed(() => store.state.count);

    function increment() {
      store.commit("increment");
    }

    function decrement() {
      store.commit("decrement");
    }

    return { count, increment, decrement };
  }
};
</script>

<style scoped>
div{
    padding-top: 1rem;
    padding-bottom: 1rem;
    margin-right: auto;
    margin-left: auto;
    width: 40%;
    background-color: grey;
}

P{
    font-size: 48px;
    padding: 3rem;
    margin-right: auto;
    margin-left: auto;
    width: 50%;
    background-color: skyblue;
}

.tambah{
    width: 25%;
    padding: 0.5rem;
    margin-top: 1rem;
    color: white;
    background-color: green;
}

.kurang{
    width: 25%;
    padding: 0.5rem;
    margin-top: 1rem;
    color: white;
    background-color: red;
}
</style>