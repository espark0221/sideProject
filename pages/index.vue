<template>
<!--  <modal-component v-model="modalShow"/>-->
<!--  <input-group-component/>-->
<!--  <table-component />-->
  <book-list />
</template>

<script>
// import ModalComponent from '@/components/bootstrap/modalComponent'
// import inputGroupComponent from '@/components/bootstrap/inputGroupComponent'
// import tableComponent from '@/components/bootstrap/tableComponent'
import bookList from '~/components/test/bookList'
export default {
  name: 'IndexPage',
  components: {
    // ModalComponent,
    // inputGroupComponent,
    // tableComponent,
    bookList
  },
  data () {
    return {
      modalShow: false
    }
  }
}
</script>
