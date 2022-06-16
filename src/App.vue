<template>
  <header id="header">
    <img src="./assets/logo-black.svg" alt="Martin black logo" />
    <h1 id="title">2902 Tools comparator</h1>
  </header>
  <main>
    <section>
      <h2>Select the articles inside the machine:</h2>
      <p>/Don't select the removable article/</p>
      <articleSelector :articles="articlesArray" :buttonChangerValue="true"
        @article-to-selected-list="selectingArticles" class="center" />
      <ul>
        <li class="articleInMachine" v-for="(selectedArticles, index) in selectedArticlesArray"
          :key="selectedArticles.number">{{
              selectedArticles.number
          }}
          <button id="delete-btn" @click="deleteFromSelectedList(index)"><i class="fa-solid fa-trash-can fa-s"></i></button>
        </li>
      </ul>
    </section>
    <section>
      <h2>Select the removable article:</h2>
      <articleSelector :articles="articlesArray" :buttonChangerValue="false"
        @listing-removable-tools="listingRemovableTools" />
      <ul>
        <li class="removable-tool" v-for="removableTools in removableToolsArray" :key="removableTools">
          <span class="removable-tool-num"> {{ removableTools }} </span>
        </li>
      </ul>
    </section>


  </main>
</template>

<script>
import articleSelector from './components/articleSelector.vue'


export default {
  name: "App",
  components: {
    articleSelector
  },
  data() {
    return {
      article: "",
      articlesArray: [
        {
          number: "223-014-00",
          tools: [750, 751, 850, 859, 883]
        },
        {
          number: "226-261-00",
          tools: [9, 70, 272, 275, 332, 310, 820]
        },
        {
          number: "226-275-00",
          tools: [186, 556, 172, 70, 310, 943, 272, 14, 850, 676]
        },
        {
          number: "283-200-00",
          tools: [3, 14, 184, 272, 516, 608, 803, 851, 880]
        },
        {
          number: "293-291-00",
          tools: [803, 969, 971]
        },
        {
          number: "293-795-00/-796/-810",
          tools: [155, 9, 15, 172, 224, 223, 272, 305, 601, 666, 821, 850, 851]
        },
        {
          number: "303-041-00",
          tools: [4, 17, 11, 70, 272, 310, 313, 504, 505, 517, 614, 692, 800, 821, 852, 880, 883, 900]
        },
        {
          number: "365-601-00",
          tools: [4, 9, 145, 70, 71, 76, 86, 272, 313, 332, 310, 454, 771, 850]
        },
        {
          number: "365-602-00",
          tools: [9, 12, 272, 305, 332]
        },
        {
          number: "393-0331-000",
          tools: [756, 738, 860, 9, 332]
        },
        {
          number: "393-0332-000",
          tools: [756, 738, 860, 9, 332]
        },
        {
          number: "393-080-00",
          tools: [9, 12, 184, 272, 305, 309, 680, 803, 852, 857],
        },
        {
          number: "394-0041-001",
          tools: [756, 738, 860, 784]
        },
        {
          number: "513-1100-000",
          tools: [882, 944, 535, 506, 931, 854, 512, 290, 771, 15, 18, 4, 303, 350, 70, 316, 870, 654]
        },
        {
          number: "573-0104-001",
          tools: [3, 4, 6, 9, 18, 14, 74, 110, 270, 290, 303, 306, 350, 453, 771, 807, 823, 852]
        },
        {
          number: "573-021/-022/-103-000",
          tools: [4, 20, 9, 12, 18, 49, 15, 160, 70, 75, 91, 76, 110, 183, 290, 303, 306, 325, 316, 327, 350, 401, 420, 459, 506, 512, 529, 535, 648, 654, 759, 771, 770, 781, 782, 828, 806, 807, 850, 852, 854, 870, 882, 910, 931, 933, 942, 944, 954, 957],
        },
        {
          number: "575-0127-001",
          tools: [120, 220, 221, 272, 454, 750, 751, 851, 860, 883]
        },
        {
          number: "575-0180-002",
          tools: [4, 9, 14, 70, 120, 113, 270, 272, 305, 310, 311, 313, 453, 657, 686, 771, 803, 850, 854, 956, 302]
        },
        {
          number: "575-090-000",
          tools: [4, 9, 70, 120, 92, 222, 272, 313, 305, 332, 311, 406, 461, 454, 516, 665, 775, 850, 843]
        },
        {
          number: "575-150-000",
          tools: [9, 230, 272, 305, 516, 608, 852, 914]
        },
        {
          number: "575-200-000",
          tools: [3, 9, 75, 98, 197, 272, 305, 651, 661, 637, 802, 852, 857]
        },
        {
          number: "575-290-000",
          tools: [9, 103, 202, 272, 305, 369, 662, 803, 800, 825, 850]
        },
        {
          number: "603-141-000",
          tools: [20, 9, 154, 155, 272, 458, 461, 513, 621, 802, 860]
        },
        {
          number: "743-065-000",
          tools: [154, 4, 9, 272, 302, 461, 556, 676, 750, 751, 802, 860],
        },
        {
          number: "753-2005-000",
          tools: [826, 759, 166, 270, 860, 461]
        },
        {
          number: "753-3077-002",
          tools: [776, 834, 956, 803, 751, 766, 559, 800, 181, 272, 72, 74, 682, 36, 428, 9, 318, 305, 332, 14, 369, 2, 301]
        },
        {
          number: "753-4924-000",
          tools: [803, 776, 964, 800, 164, 165, 145, 272, 14, 453, 4, 302, 9, 305, 36, 428]
        },
        {
          number: "K508030-004",
          tools: [883, 820, 199, 773, 507, 561, 176, 628, 766, 691, 887, 872, 272, 27, 22, 372, 12, 325, 302, 304, 851, 860]
        },
        {
          number: "K508030-044",
          tools: [883, 820, 835, 773, 775, 218, 973, 734, 519, 821, 872, 887, 766, 675, 583, 691, 176, 272, 286, 27, 22, 12, 461, 2, 43, 423, 321, 304, 302, 372, 325, 852, 860]
        },
        {
          number: "K508030-070",
          tools: [803, 883, 775, 741, 146, 457, 766, 800, 178, 172, 177, 144, 166, 272, 453, 2, 321, 325, 423, 305, 860, 279, 690, 691]
        }
      ],
      buttonChangerValue: 'true',
      selectedArticlesArray: [],
      removableToolsArray: []
    };
  },
  methods: {
    selectingArticles(index) {
      this.selectedArticlesArray.push(this.articlesArray[index]);
    },
    deleteFromSelectedList(index) {
      this.selectedArticlesArray.splice(index, 1);
    },
    listingRemovableTools(index) {
      // The selected article tools push into a new array
      let toolsArray = [];
      this.selectedArticlesArray.map((element) => { toolsArray.push(...element.tools) });
      // Sort the new array elements (remove the duplicates)
      let sortedToolsList = [...new Set(toolsArray)];
      // Create a variable for the removable article tools list
      let removableArticle = this.articlesArray[index].tools;
      //  Delete the necessary tools from the removable tools list (Result: we have only the removable tools)
      sortedToolsList.map((element) => {
        if (removableArticle.indexOf(element) > 0) {
          removableArticle.splice(removableArticle.indexOf(element), 1);
        }
      });
      //Removable tools ascending order
      this.removableToolsArray = removableArticle.sort(function (a, b) { return a - b });
    }
  }
};
</script>

<style>
@import url(/style.css);
</style>

