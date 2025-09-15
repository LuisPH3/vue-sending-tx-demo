<template>
  <main>
    <metamask-send-tx-button></metamask-send-tx-button>
  </main>
</template>

<script>
import {defineComponent} from "vue";
import MetamaskSendTxButton from "@/components/MetamaskSendTxButton.vue";

export default defineComponent({
  components: {MetamaskSendTxButton}
})
</script>
