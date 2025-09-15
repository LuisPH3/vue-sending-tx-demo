<template>
  <main>
    <metamask-test-button></metamask-test-button>
  </main>
</template>

<script>
import {defineComponent} from "vue";
import MetamaskTestButton from "@/components/MetamaskTestButton.vue";

export default defineComponent({
  components: {MetamaskTestButton}
})
</script>
