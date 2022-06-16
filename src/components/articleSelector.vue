<template>
  <select class="selector" v-model="selectedArticle">
    <option v-for="(article, index) in articles" :key="article" :value="index">{{ article.number }}
    </option>
  </select>
  <button class="btn" v-if="buttonChangerValue" @click="articleToSelect">Add item</button>
  <button class="btn" v-if="!buttonChangerValue" @click="$emit('listingRemovableTools', this.selectedArticle)">compare</button>
</template>

<script>
export default {
  name: 'articleSelector',
  props:
    ['articles', 'buttonChangerValue'],
  data() {
    return {
      selectedArticle: '',
    }
  },
  emits: ["articleToSelectedList", "listingRemovableTools"],
  methods: {
    articleToSelect() {
      this.$emit('articleToSelectedList', this.selectedArticle);
      this.selectedArticle = '';
    }
  }

}
</script>