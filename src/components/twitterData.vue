<template>
  <div>
    <!-- toggle button for changing the view -->
    <button id="grid">Toggle</button>
  </div>
</template>

<script>
export default {
    // mounted will help adding event listener after the page is mounted
  mounted() {
    this.show_tweet();
    let grid = document.getElementById(`grid`);
    grid.addEventListener(`click`, this.column_list);
  },
//   methods contain the functions
  methods: {
    // show tweet will display data from data 
    show_tweet() {
      let box = document.getElementById(`box`);
      for (let i = 0; i < this[`data`].length; i++) {
        box[`innerHTML`] += `<div class="content_item">
            <h2> ${this[`data`][i][`user`]} </h2>
            <p>${this[`data`][i][`date`]}</p>
            <h2>${this[`data`][i][`tweet`]}</h2>
            </div>`;
      }
    },
    // column_list function will check if the box has style property grid auto flow is row or column and convert them 
    column_list() {
      let box = document.getElementById(`box`);
     if(box[`style`][`gridAutoFlow`] === `column`){
        box[`style`][`gridAutoFlow`] =`row`;
     } else {
        box[`style`][`gridAutoFlow`] =`column`;
     }
    },
  },
// data has all the data regarding tweets
  data() {
    return {
      data: [
        {
          tweet: `be Honest`,
          user: `satinder`,
          date: `02-02-2022`,
        },
        {
          tweet: `be Positive`,
          user: `sam`,
          date: `03-05-2022`,
        },
        {
          tweet: `be Humble`,
          user: `nav`,
          date: `05-05-2010`,
        },
        {
          tweet: `be Strong`,
          user: `nit`,
          date: `04-02-2021`,
        },
      ],
    };
  },
};
</script>
<style scoped>

</style>