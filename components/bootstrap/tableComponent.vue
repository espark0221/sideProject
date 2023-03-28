<template>
  <div>
    <b-form-group
      label-for="select"
      label-cols-md="4"
    >
      <div>
        <b-form-select
          id="select"
          v-model="teamSelect"
          :options="team"
        ></b-form-select>
        <b-form-select
          id="select"
          v-model="checkSelect"
          :options="checkOutYn"
        ></b-form-select>
      </div>
    </b-form-group>

    <b-table
      :items="items"
      :fields="fields"
      :select-mode="selectMode"
      responsive="sm"
      ref="selectableTable"
      selectable
      @row-selected="onRowSelected"
    >
      <!-- Example scoped slot for select state illustrative purposes -->
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
<!--    <p>-->
<!--      Selected Rows:<br>-->
<!--      {{ selected }}-->
<!--    </p>-->
  </div>
</template>

<script>
export default {
  data () {
    return {
      team: ['팀별도서', 'FE팀', 'BE팀', 'UI팀', 'DX팀', '운영팀', '관리팀'],
      checkOutYn: ['대여여부', '대여', '반납', '대여중'],
      fields: ['최신인기여부', '번호', '도서명', '대여여부'],
      items: [
        { 최신인기여부: '최신', 번호: 40, 도서명: 'bookOne', 대여여부: '대여' },
        { 최신인기여부: '인기', 번호: 21, 도서명: 'bookTwo', 대여여부: '반납' },
        { 최신인기여부: '최신', 번호: 89, 도서명: 'bookThree', 대여여부: '대여중' },
        { 최신인기여부: '인기', 번호: 38, 도서명: 'bookFour', 대여여부: '반납' }
      ],
      teamSelect: '팀별도서',
      checkSelect: '대여여부',
      selected: []
    }
  },
  methods: {
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
      // Rows are indexed from 0, so the third row is index 2
      this.$refs.selectableTable.selectRow(2)
    },
    unselectThirdRow () {
      // Rows are indexed from 0, so the third row is index 2
      this.$refs.selectableTable.unselectRow(2)
    }
  }
}
</script>
