<template>
  <fieldset>
    <button @click="sendTx()">Send tx with zero gas price</button>
  </fieldset>
</template>

<script>
import { ethers } from "ethers";

export default {
  methods: {
    async sendTx() {
      console.log('window.ethereum', window.ethereum)
      if (window.ethereum == null) {
        alert('MetaMask not installed')
        return
      }

      const provider = new ethers.BrowserProvider(window.ethereum)
      console.log('provider', provider)
      await provider.send('eth_requestAccounts', [])
      const signer = await provider.getSigner()
      const address = await signer.getAddress()
      console.log('address', address)

      const tx = await signer.sendTransaction({
        to: "0x000000000000000000000000000000000000dead",
        value: ethers.parseEther("0"),
        gasPrice: ethers.parseEther("0"),
        gasLimit: 50_000n,
      })

      console.log('transaction:', tx)
      alert('sent successfully')
    }
  }
}
</script>
