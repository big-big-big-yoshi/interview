<template>
  <div>
    <div class="selection_container">
      <div class="dimension_contianer">
        <h3 style="text-align: left">Row Selection</h3>
        <ul style="list-style-type: none; flex:1; text-align: left; padding: 0px">
          <li
            v-for="(item, index) in row_dimensions"
            :key="item.value"
            v-on:click="item.selected = !item.selected"
            class="dim_selector"
          >
            <span v-if="item.selected">X-</span>
            <span v-else>O-</span>
            <span>{{ item.value }}</span>
          </li>
        </ul>
      </div>
      <div class="dimension_contianer">
        <h3 style="text-align: left">Column Selection</h3>
        <ul style="list-style-type: none; flex:1; text-align: left; padding: 0px">
          <li
            v-for="(item, index) in col_dimensions"
            :key="item.value"
            v-on:click="item.selected = !item.selected"
          >
            <span v-if="item.selected">X-</span>
            <span v-else>O-</span>
            <span>{{ item.value }}</span>
          </li>
        </ul>
      </div>
    </div>

    <!-- Pivot Table output goes here. -->

    <!-- <pre style="text-align:left;">{{raw_data}}</pre> -->
  </div>
</template>

<script>
import source_data from "./data.js"
export default {
  name: "pivot",
  props: {},
  data: function () {
    return {
      row_dimensions: [
        {
          value: "region",
          selected: false,
        },
        {
          value: "sales_rep",
          selected: false,
        },
        {
          value: "item",
          selected: false,
        },
        {
          value: "item_category",
          selected: false,
        },
      ],
      col_dimensions: [
        {
          value: "region",
          selected: false,
        },
        {
          value: "sales_rep",
          selected: false,
        },
        {
          value: "item",
          selected: false,
        },
        {
          value: "item_category",
          selected: false,
        },
      ],
      raw_data: source_data
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.selection_container {
  display: flex;
}
.dimension_contianer{
    margin-right: 20px;
}
.dim_selector{
    cursor:pointer;
}
</style>
