<template>
  <hot-table :settings="hotSettings">
    <hot-column :width="250">
      <custom-renderer hot-renderer></custom-renderer>
    </hot-column>
  </hot-table>
</template>

<script>
import Vue from "vue";
import { HotTable } from "@handsontable/vue";
import Handsontable from "handsontable";

const CustomRenderer = {
  template:
    '<div><i style="color: #a9a9a9">Row: {{row}}, column: {{col}},</i> value: {{value}}</div>',
  data: function() {
    return {
      hotInstance: null,
      TD: null,
      row: null,
      col: null,
      prop: null,
      value: null,
      cellProperties: null
    };
  }
};

export default {
  el: "#custom-renderer-example",
  data: function() {
    return {
      hotSettings: {
        data: Handsontable.helper.createSpreadsheetData(10, 10),
        licenseKey: "non-commercial-and-evaluation",
        autoRowSize: false,
        autoColumnSize: false
      }
    };
  },
  components: {
    HotTable,
    HotColumn,
    CustomRenderer
  }
};
</script>