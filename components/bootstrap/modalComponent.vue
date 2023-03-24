<template>
  <div>
    <b-button id="show-btn" @click="showModal">모달 팝업 열기</b-button>

    <b-modal ref="my-modal" hide-footer title="아이디벨 도서 관리 시스템">
      <div class="d-block text-center">
        <h3>도서 대여 확인 문구</h3>
      </div>
      <b-button class="mt-3" variant="outline-danger" block @click="hideModal">다른 동작하기</b-button>
      <b-button class="mt-3" variant="outline-warning" block @click="hideModal">모달 팝업 닫기</b-button>
    </b-modal>
  </div>
</template>

<script>
export default {
  name: 'modalComponent',
  methods: {
    showModal () {
      this.$refs['my-modal'].show()
    },
    hideModal () {
      this.$refs['my-modal'].hide()
    }
  }
}
</script>
