<template>
  <div class="col">
    <b-col cols="12">
      <h4 id="text">Search Music</h4>
      <input type="text" v-model="textSearch" placeholder="Search" />
      <button @click="searchData()">Search</button>
    </b-col>
    <b-row>
      <b-col cols="12">
        <div class="mt-4" v-for="list in playList" :key="list.trackId">
          <b-card
            no-body
            class="overflow-hidden"
            style="width: 100%"
            border-variant="info"
          >
            <b-row no-gutters >
              
              <b-col md="2" >
                <b-card-img
                  :src="list.artworkUrl60"
                  :alt="list.artistName"
                  class="rounded-0"
                ></b-card-img>
              </b-col>
              <b-col md="10">
                <b-card-body :title="list.trackName">
                  {{ list.trackId }}
                <b-card-text>
                    <audio controls>
                      <source :src="list.previewUrl" type="audio/mpeg" />
                    </audio>
                    <b-card-text :title="list.releaseDate">
                      {{ list.releaseDate }}
                    </b-card-text>
                    <b-card-text :title="list.shortDescription">
                      {{ list.shortDescription }}
                    </b-card-text>
                  </b-card-text>
                </b-card-body>
              </b-col>
            </b-row>
          </b-card>
        </div>
      </b-col>
    </b-row>
  </div>
</template>
<script>
import axios from "axios";
export default {
  data() {
    return {
      playList: null,
      textSearch: "",
    };
  },
  methods: {
    searchData() {
      axios
        .get(
          "https://itunes.apple.com/search?term=+" +
            this.textSearch +
            "&limit=100"
        )
        .then((response) => {
          this.playList = response.data.results.slice(0, 20);
        })
        .catch((err) => {
          console.log(err);
        });
    },
  },
};
</script>
<style>
#text {
  color: rgb(0, 0, 0);
}
</style>