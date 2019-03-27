<template>
  <div>
    <b-table
      striped
      hover
      :items="items"
      :per-page="perPage"
      :current-page="currentPage"
      :fields="fields"
    />
    <b-pagination
      v-model="currentPage"
      :total-rows="rows"
      :per-page="perPage"
      aria-controls="myTable"
      align="center"
    />
  </div>
</template>

<script>
export default {
  name: "Table",
  props: ["items"],
  data() {
    return {
      perPage: 10,
      currentPage: 1,
      fields: [
        { key: "ID", sortable: true },
        { key: "Name", sortable: true },
        { key: "Description", sortable: false },
        { key: "Date", sortable: true },
        { key: "Amount", sortable: true }
      ]
    };
  },
  computed: {
    rows() {
      return this.items.length;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  width: 100%;
  padding: 0;
  text-align: center;
  color: #42b983 !important;
}
li {
  display: inline-block;
  height: 100px;
  width: 100%;
  margin: 0 10px;
  background-color: #42b983;
}
li a {
  color: #42b983;
}
</style>