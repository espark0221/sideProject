<template>
  <section>
    <div id="test">
      <table-component id="table"></table-component>
    </div>
  </section>
</template>

<script>
import tableComponent from '@/components/bootstrap/tableComponent'
export default {
  name: 'IndexPage',
  components: {
    tableComponent
  },
  data () {
    return {
    }
  }
}
</script>
<style>
#test{
  margin-top: 150px;
  margin-left: 30px;
  margin-right: 30px;
}
#table{
  text-align: center;
  width: 60%;
  margin: auto;
}
</style>
