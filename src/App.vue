<template>
  <div id="app">
    <button @click="handleAddRecord">add</button>
    <ejs-grid
      id="my_grid"
      ref="myGrid"
      :dataSource="data"
      :editSettings="editSettings"
    >
    </ejs-grid>
  </div>
</template>

<script>
import Vue from "vue";
import { GridPlugin, Edit } from "@syncfusion/ej2-vue-grids";

Vue.use(GridPlugin);

export default {
  data() {
    return {
      data: [
        { OrderID: 10248, CustomerID: "VINET", Freight: 32.38 },
        { OrderID: 10249, CustomerID: "TOMSP", Freight: 11.61 },
        { OrderID: 10250, CustomerID: "HANAR", Freight: 65.83 },
        { OrderID: 10251, CustomerID: "VICTE", Freight: 41.34 },
        { OrderID: 10252, CustomerID: "SUPRD", Freight: 51.3 },
        { OrderID: 10253, CustomerID: "HANAR", Freight: 58.17 },
        { OrderID: 10254, CustomerID: "CHOPS", Freight: 22.98 },
        { OrderID: 10255, CustomerID: "RICSU", Freight: 148.33 },
        { OrderID: 10256, CustomerID: "WELLI", Freight: 13.97 },
      ],
      editSettings: {
        // allowEditing: true,
        allowAdding: true,
        // allowDeleting: true,
      },
      toolbar: [],
    };
  },
  mounted() {
    this.clearBanner();
  },
  methods: {
    clearBanner() {
      const childForm = Array.from(document.body.childNodes);
      childForm.forEach((v) => {
        if (v.nodeName === "DIV" && v.style.position === "fixed") {
          v.style.display = "none";
        }
      });
    },
    handleAddRecord() {
      this.$refs.myGrid.addRecord();
    },
  },
  provide: {
    grid: [Edit],
  },
};
</script>

<style>
@import "../node_modules/@syncfusion/ej2-base/styles/material.css";
@import "../node_modules/@syncfusion/ej2-buttons/styles/material.css";
@import "../node_modules/@syncfusion/ej2-calendars/styles/material.css";
@import "../node_modules/@syncfusion/ej2-dropdowns/styles/material.css";
@import "../node_modules/@syncfusion/ej2-inputs/styles/material.css";
@import "../node_modules/@syncfusion/ej2-navigations/styles/material.css";
@import "../node_modules/@syncfusion/ej2-popups/styles/material.css";
@import "../node_modules/@syncfusion/ej2-splitbuttons/styles/material.css";
@import "../node_modules/@syncfusion/ej2-vue-grids/styles/material.css";
</style>
