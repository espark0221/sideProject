<template>
  <b-table-simple>
    <colgroup><col><col></colgroup>
    <colgroup><col><col><col></colgroup>
    <colgroup><col><col></colgroup>
    <b-thead head-variant="dark">
      <b-tr>
        <b-th colspan="2">Region</b-th>
        <b-th colspan="3">Clothes</b-th>
        <b-th colspan="2">Accessories</b-th>
      </b-tr>
      <b-tr>
        <b-th>Country</b-th>
        <b-th>City</b-th>
        <b-th>Trousers</b-th>
        <b-th>Skirts</b-th>
        <b-th>Dresses</b-th>
        <b-th>Bracelets</b-th>
        <b-th>Rings</b-th>
      </b-tr>
    </b-thead>
    <b-tbody>
      <b-tr>
        <b-th rowspan="3">Belgium</b-th>
        <b-th class="text-right">Antwerp</b-th>
        <b-td>56</b-td>
        <b-td>22</b-td>
        <b-td>43</b-td>
        <b-td variant="success">72</b-td>
        <b-td>23</b-td>
      </b-tr>
      <b-tr>
        <b-th class="text-right">Utrecht</b-th>
        <b-td>80</b-td>
        <b-td variant="danger">12</b-td>
        <b-td>43</b-td>
        <b-td>36</b-td>
        <b-td variant="warning">19</b-td>
      </b-tr>
    </b-tbody>
    <b-tfoot>
      <b-tr>
        <b-td colspan="7" variant="secondary" class="text-right">
          Total Rows: <b>5</b>
        </b-td>
      </b-tr>
    </b-tfoot>

  </b-table-simple>
</template>

<script>
// colgroup 테이블에서 서식 지정을 위해 하나 이상의 열을 그룹으로 묶을 때 사용
export default {

}
</script>
