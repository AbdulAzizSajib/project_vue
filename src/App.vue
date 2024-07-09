<script>
import { ref } from "vue";
export default {
  data() {
    return {
      name: "SAJIB",
      status: false, // if boolean
      statusString: "active", // if string
      tasks: ["task one", "task two", "task three "],
      link: "https://google.com",
      link2: "https://facebook.com",
    };
  },

  // setup() {
  //   const count = ref(0);

  //   function increment() {
  //     count.value++;
  //   }

  //   function decrement(){
  //     count.value--;
  //   }
  //   return { count, increment, decrement };
  // },

  setup() {
    const items = ref(['Apple', 'Banana', 'Cherry']);

    function addItem(item) {
      items.value.push(item);
    }

    return {
      items,
      addItem
    };
  }

};
</script>

<template>
  <div>
    <h2>{{ name }}</h2>
    <!-- V-if , v-else , v-else-if -->
    <h2 v-if="status">Is he active?</h2>
    <h2 v-else>He is not active</h2>
  </div>
  <!-- v-else-if -->
  <div>
    <h2 v-if="statusString === 'active'">He is Active</h2>
    <h2 v-else-if="statusString === 'loading'">Loading</h2>
    <h2 v-else>He is inactive</h2>
  </div>
  <!-- v-for -->
  <div>
    <h2>Task</h2>
    <ul>
      <li v-for="task in tasks" :key="task">{{ task }}</li>
    </ul>
  </div>
  <!-- v-bind -->
  <div>
    <a v-bind:href="link"> Click For Google</a>
    <a :href="link2"> Click For fb</a>
  </div>
  <!-- v-on / @ -->
  <div>
    <button @click="status = !status">Toggle</button>
  </div>
  <!-- ref() -->
  <div>
    <h2>{{ count }}</h2>
    <button @click="increment">Increment</button>
    <button @click="decrement">Increment</button>
  </div>
  <div>
    <ul>
      <li v-for="item in items" :key="item">{{ item }}</li>
    </ul>
    <button @click="addItem('Date')">Add Date</button>
  </div>
</template>
