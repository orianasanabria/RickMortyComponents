<template>
  <div v-if="characters.length > 0" id="characters" class="container mt-5">
    <div class="card-group">
      <div class="row">
        <div
          v-for="(character, i) in characters"
          :key="i"
          class="card col-lg-6 col-12 mb-3 px-0 bg-dark"
        >
          <div class="row g-4">
            <div class="col-md-4">
              <img :src="character.image" alt="Character Image" width="100%" />
            </div>
            <div class="col-md-8 d-flex align-items-center">
              <div class="card-body">
                <h3 class="card-title text-light">{{ character.name }}</h3>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Characters",
  data() {
    return {
      characters: [],
    };
  },
  methods: {
    async getData() {
      const url = "https://rickandmortyapi.com/api/character";
      try {
        const req = await axios(url);
        if (!req) return;
        this.characters = req.data.results;
      } catch (error) {
        console.log(error);
      }
    },
  },
  created() {
    this.getData();
  },
};
</script>

<style>
.container {
  box-sizing: border-box;
}
</style>
