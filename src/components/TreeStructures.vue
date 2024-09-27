<template>
  <div>
    <tree :data="treeData" :options="options" />
  </div>
</template>

<script>
import * as Tree from 'd3';

export default {
  components: {
    Tree,
  },
  data() {
    return {
      treeData: {
        name: 'Root Node',
        children: [
          {
            name: 'Child Node 1',
            children: [],
          },
          {
            name: 'Child Node 2',
            children: [],
          },
        ],
      },
      options: {
        orientation: 'vertical', // Top-down
        nodeSize: {
          x: 200,
          y: 100,
        },
        separation: {
          siblings: 1,
          nonSiblings: 1,
        },
        renderNode: (node) => {
          return `<div style="padding:10px;background:#ACE600;border-radius:5px;">${node.data.name}</div>`;
        },
      },
    };
  },
};
</script>

<style>
/* Add any necessary styles */
</style>
