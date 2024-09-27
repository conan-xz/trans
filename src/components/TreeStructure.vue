<template>
    <div>
      <vue3-tree :nodes="treeData" :data="treeData" :options="treeViewOptions" @node-click="handleClick" />
    </div>
  </template>
  
  <script>
  import Vue3Tree from 'vue3-tree';
  
  export default {
    components: {
      Vue3Tree,
    },
    data() {
      return {
        treeData: [
          {
            id: 1,
            label: '节点 1',
            children: [
              {
                id: 11,
                label: '子节点 1.1',
                children: [],
              },
            ],
          },
          {
            id: 2,
            label: '节点 2',
            children: [
              {
                id: 21,
                label: '子节点 2.1',
                children: [],
              },
            ],
          },
        ],
        treeViewOptions: {
          nodeData: {
            name: 'label',
            children: 'children',
          },
          // 默认不展开抽屉
          defaultExpandedKeys: [],
        },
      };
    },
    methods: {
      handleClick(node) {
        console.log('Clicked Node:', node);
        // Get the tree instance
        const treeInstance = this.$refs.tree.vue3Tree;
        // Toggle the expansion state of the clicked node
        treeInstance.toggleNode(node.id);
      },
    },
  };
  </script>