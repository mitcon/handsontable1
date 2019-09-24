<template>
  <div id="app">
    <hot-table :settings="hotSettings"></hot-table>
  </div>
</template>

<script>
import Vue from "vue";
import { HotTable } from "@handsontable/vue";
import Handsontable from "handsontable";

export default {
  el: "#app",
  data: function() {
    return {
      hotSettings: {
        data: Handsontable.helper.createSpreadsheetData(6, 10),
        colHeaders: true
      }
    };
  },
  components: {
    HotTable
  }
};
</script>

<style src="../node_modules/handsontable/dist/handsontable.full.css" />