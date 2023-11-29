<template>
      <IndexBar :index-list="indexList">
            <div v-for="index in indexList" :key="index">
                  <IndexAnchor :index="index.toString()"></IndexAnchor>
                  <div v-for="block in contentBlocks" :key="block.title + index">
                        <Cell :title="block.title" :label="block.price" :value="block.description" />
                  </div>
            </div>
      </IndexBar>
</template>

<script setup lang="ts">
import { IndexBar, IndexAnchor, Cell } from "vant";

// Just add to indexlist to add more items. It will auto create the index bar
const indexList = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
const contentBlocks = [
      {
            title: "Product 1",
            description:
                  "This is a description 2 very long text will be truncated to 2 lines max and end with ellipsis",
            price: "$19.99",
      },
      {
            title: "Product 2",
            description:
                  "This is a description 2 very long text will be truncated to 2 lines max and end with ellipsis",
            price: "$29.99",
      },
      {
            title: "Product 3",
            description:
                  "This is a description 2 very long text will be truncated to 2 lines max and end with ellipsis and of course it will be truncated to 2 lines max and end with ellipsis and of course will be truckated to 2 lines max ",

            price: "$39.99",
      },
      {
            title: "Product 4",

            description:
                  "This is a description 2 very long text will be truncated to 2 lines max and end with ellipsis",
            price: "$49.99",
      },
      {
            title: "Product 5",
            description:
                  "This is a description 2 very long text will be truncated to 2 lines max and end with ellipsis",
            price: "$59.99",
      },
];
</script>

<style>
.van-index-bar__sidebar {
      flex-direction: row;
      padding-left: 100px;
      padding-top: 40px;
      position: fixed;
      top: 0;
      z-index: 999;
      margin-top: 0;
}
</style>
