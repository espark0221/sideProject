<!--20230328 박은솔 (도서 리스트)-->
<template>
  <div>
    <input type="text" class="header" placeholder="header area">
    <b-form-group
      label-for="select"
    >
        <b-form-select
          v-model="teamSelect"
          :options="team"
        ></b-form-select>
        <b-form-select
          v-model="checkSelect"
          :options="checkOutYn"
        ></b-form-select>
      <b-form-input
        v-model="searchText"
        placeholder="검색어를 입력해주세요"
      ></b-form-input>
      <b-button id="searchBtn" class="btn btn-dark" @click="search()">검색</b-button>
    </b-form-group>

    <b-table
      :items="items"
      :fields="fields"
      :select-mode="`multi`"
      responsive="sm"
      ref="selectableTable"
      selectable
      @row-selected="onRowSelected"
    >
      <template #cell(selected)="{ rowSelected }">
        <template v-if="rowSelected">
          <span aria-hidden="true">&check;</span>
          <span class="sr-only">Selected</span>
        </template>
        <template v-else>
          <span aria-hidden="true">&nbsp;</span>
          <span class="sr-only">Not selected</span>
        </template>
      </template>
    </b-table>
    <p>
      <!--      <b-button size="sm" @click="selectAllRows">Select all</b-button>-->
      <!--      <b-button size="sm" @click="clearSelected">Clear selected</b-button>-->
      <!--      <b-button size="sm" @click="selectThirdRow">Select 3rd row</b-button>-->
      <!--      <b-button size="sm" @click="unselectThirdRow">Unselect 3rd row</b-button>-->
    </p>
  </div>
</template>

<script>
export default {
  data () {
    return {
      // team: ['팀별도서', 'FE팀', 'BE팀', 'UI팀', 'DX팀', '운영팀', '관리팀'],
      team: [
        { value: null, text: '최신 인기 여부', disabled: true },
        { value: '최신', text: '최신' },
        { value: '인기', text: '인기' }
      ],
      // checkOutYn: ['대여여부', '대여', '반납', '대여중'],
      checkOutYn: [
        { value: null, text: '대여여부', disabled: true },
        { value: 'checkout', text: '대여' },
        { value: 'return', text: '반납' },
        { value: 'UI', text: '대여중' }
      ],
      fields: ['최신인기여부', '번호', '도서명', '대여여부'],
      items: [
        { 최신인기여부: '최신', 번호: 40, 도서명: 'bookOne', 대여여부: '대여' },
        { 최신인기여부: '인기', 번호: 21, 도서명: 'bookTwo', 대여여부: '반납' },
        { 최신인기여부: '최신', 번호: 89, 도서명: 'bookThree', 대여여부: '대여중' },
        { 최신인기여부: '인기', 번호: 38, 도서명: 'bookFour', 대여여부: '반납' }
      ],
      teamSelect: null,
      checkSelect: null,
      selected: [],
      searchText: ''
    }
  },
  methods: {
    search () {
      console.log(this.teamSelect)
      console.log(this.checkSelect)
      console.log(this.searchText)
    },
    onRowSelected (items) {
      this.selected = items
    },
    selectAllRows () {
      this.$refs.selectableTable.selectAllRows()
    },
    clearSelected () {
      this.$refs.selectableTable.clearSelected()
    },
    selectThirdRow () {
      this.$refs.selectableTable.selectRow(2)
    },
    unselectThirdRow () {
      this.$refs.selectableTable.unselectRow(2)
    }
  }
}
</script>
<style>
.header{
  width: 90%;
  height: 100px;
  display: block;
  margin-top: 5rem;
  margin-left: 4rem;
  margin-right: 4rem;
  text-align: center;
}
.custom-select{
  width: 20%;
  display: inline;
  vertical-align: middle;
  margin-top: 4rem;
  margin-left:4rem;
}
.form-control{
  display: inline;
  width: 40%;
  vertical-align: middle;
  margin-top: 4rem;
  margin-left: 4rem;
  margin-right: 4rem;
}
.form-group{
  display: inline;
}
.btn{
  display: inline;
  margin-top: 4rem;
  vertical-align: middle;
}
.table-responsive-sm{
  margin-top: 5rem;
  margin-left: 4rem;
}

</style>
