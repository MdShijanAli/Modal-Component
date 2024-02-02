<template>
  <div class="home">
     <ModalComponent @close="toggleModal" :modalActive="modalActive">
      <div class="modal-content">
         <h1>This is a Modal Header</h1>
         <p>This is Modal Messag4</p>
      </div>
     </ModalComponent>
     <button @click="toggleModal">Open Modal</button>
  </div>
</template>

<script>
import ModalComponent from '@/components/ModalComponent.vue';
import { ref } from 'vue';
export default {
  name: 'HomeView',
  components: {
    ModalComponent,
  },

  setup(){
    const modalActive = ref(false);

    const toggleModal = () =>{
      modalActive.value = !modalActive.value
    }

    return {modalActive,toggleModal}
  }
}
</script>


<style scoped>
.home{
  background-color: rgba(0,176, 234, 0.5);
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
.modal-content{
  display: flex;
  flex-direction: column;
}
.modal-content h1,
.modal-content p{
  margin-bottom: 16px;
}
.modal-content h1{
  font-size: 32px;
}
</style>