<template>
  <select class="selector" v-model="selecteditem">
    <option v-for="(item, index) in itemsArray" :key="item" :value="index">{{ item.number }}
    </option>
  </select>
  <button class="btn" v-if="buttonChangerValue" @click="itemToSelect">Add item</button>
  <button class="btn" v-if="!buttonChangerValue" @click="$emit('listingRemovableTools', this.selecteditem)">compare</button>
</template>

<script>
export default {
  name: 'itemSelector',
  props:
    ['itemsArray', 'buttonChangerValue'],
  data() {
    return {
      selecteditem: '',
    }
  },
  emits: ["itemToSelectedList", "listingRemovableTools"],
  methods: {
    itemToSelect() {
      this.$emit('itemToSelectedList', this.selecteditem);
      this.selecteditem = '';
    }
  }

}
</script>