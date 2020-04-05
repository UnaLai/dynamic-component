<template>
  <div class="home">
    <div v-if="showSync">
      <SyncComponent />
    </div>
    <button @click="showSync = !showSync">Toggle Sync Component</button>
  </div>
</template>

<script>
import Error from "@/components/Error.vue";
import Loading from "@/components/Loading.vue";

const SyncComponent = () => ({
  component: import("@/components/SyncComponent.vue"),
  loading: Loading,
  delay: 2000,
  error: Error
});
export default {
  name: "Home",
  components: {
    SyncComponent: SyncComponent
  },
  data() {
    return {
      showSync: false
    };
  }
};
</script>
