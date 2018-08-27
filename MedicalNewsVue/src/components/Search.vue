<template>
  <div>
      <div class="container">
       <div class="grid">
         <div class="col" v-for="item in results" :key="item.author">
         <a :href="item.url">
         <img :src="item.urlToImage">
         <div class="wrapper">
         <p class="date">{{item.publishedAt}}</p>
        <!-- <h1>{{item.author}}</h1> -->
        <h3>{{item.title}}</h3>
        <p class="text">{{item.description}}</p>
        </div>
         </a>
      </div>
      </div>
     </div>
    <!-- <button v-on:click="fetchData">Add 1</button> -->
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Search",
  data() {
    return {
      results: []
    };
  },
  methods: {
    fetchData: function() {
      axios
        .get(
          "https://newsapi.org/v2/top-headlines?sources=medical-news-today&apiKey=5dba100e14914809983c32d8f26c3740"
        )
        .then(res => (this.results = res.data.articles))
        .catch(err => console.log(err));
    }
  },
  created: function() {
    this.fetchData();
  }
};
</script>

<style>
body {
  padding: 0;
  margin: 0;
  font-family: "Roboto", sans-serif;
}
a {
  text-decoration: none;
  color: #000;
}
.container {
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 70px 0 70px;
}

@media (max-width: 600px) {
  .wrapper {
    padding: 20px;
  }
}

.grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-column-gap: 50px;
  grid-row-gap: 50px;
}
@media (max-width: 600px) {
  .grid {
    grid-template-columns: 1fr;
    grid-column-gap: 0;
    grid-row-gap: 0;
  }
  .container {
    width: 100%;
    margin: 0 auto;
    padding: 0;
  }
}
.col {
  width: 100%;
}
img {
  width: 100%;
  height: auto;
  transition: all 0.5s;
}
img:hover {
  transform: scale(1.03);
}
.date {
  color: #999;
  font-weight: 300;
}
h3 {
  font-weight: 300;

  font-size: 32px;
}
.text {
  font-family: "Open Sans", sans-serif;
  font-weight: 200;
  font-size: 18px;
}
</style>

