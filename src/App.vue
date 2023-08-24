<template>
  <div v-if="showModal">
    <Modal :header="header" :content="content" :theme="theme" @close="showModal=false">
      <button @click="showModal2=true">Close</button>
    </Modal>
    
  </div>
  <button @click="showModal=true">Open Modal</button>
  <div v-if="showModal2">
    <Modal :theme2="theme2" @close="showModal2=false">
      <span>Are you sure want to close?</span> <br>
      <button @close="showModal2=false,showModal=false">Yes</button> &nbsp;
      <button @click="showModal=true">cancel</button>
    </Modal>
  </div>
</template>

<script>
import Modal from './components/Modal.vue'
export default {
  data(){
    return {
      header: "Login Success",
      content: "Welcome naoki-kun....",
      theme: "success",
      theme2: "delete",
      showModal: false,
      showModal2: false
    }
  },
  components: {
    Modal
  }
}

</script>

<style>

</style>
