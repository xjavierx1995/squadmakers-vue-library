<template>
  <div class="blog-card">
    <div class="meta">
      <div class="photo" :style="'background-image: url('+imageUrl+')'"></div>
      <!-- <ul class="details">
        <li class="author"><a href="#"> {{ imageUrl }} </a></li>
        <li class="date">Nov. 13, 2020</li>
        <li class="tags">
          <ul>
            <li><a href="#">C++</a></li>
            <li><a href="#">Python</a></li>
            <li><a href="#">Java</a></li>
            <li><a href="#">JavaScript</a></li>
          </ul>
        </li>
      </ul> -->
    </div>
    <div class="description">
      <div class="info-title">{{ character.status }} - {{ character.species }}</div>
      <div class="info-description-name">{{ character.name }}</div>
      <div class="info-title">Last known location:</div>
      <div class="info-description">{{ character.location.name }}</div>
      <div class="info-title">First seen in:</div>
      <div class="info-description">{{ character.origin.name }}</div>
      
    </div>
  </div>
</template>
<script setup lang="ts">

import { computed } from 'vue';
interface Character {
  id: number;
  name: string;
  status: string;
  species: string;
  type: string;
  gender: string;
  image: string;
  episode: string[];
  url: string;
  created: string;
  origin: {
    name: string;
    url: string;
  };
  location: {
    name: string;
    url: string;
  };
}

const props = defineProps<{ character: Character }>()

const imageUrl = computed(() => {
  return props.character.image; 
})
</script>
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500&display=swap');
.blog-card {
  display: flex;
  flex-direction: column;
  background: #fff;
  overflow: hidden;
  z-index: 0;

  border-radius: 10px;
  border: 1px solid #E0E0E0;

  &:hover .photo {
    transform: scale(1.3) rotate(3deg);
  }

  .meta {
    position: relative;
    z-index: 0;
    height: 200px;
  }
  .photo {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    background-size: cover;
    background-position: center;
    transition: transform 0.2s;
  }

  .description {
    padding: 1rem;
    background: #fff;
    position: relative;
    z-index: 1;

    font-family: Montserrat;
    font-weight: 500;
    line-height: 15px;
    text-align: left;
    letter-spacing: 0em;

    .info-title {
      font-size: .8em;
      color: #828282;
    }

    .info-description-name {
      font-size: 1.2em;
      color: #000000;
      margin-bottom: 10px;
    }
    .info-description {
      font-size: 12px;
      color: #000000;
      margin-bottom: 10px;

      text-overflow: ellipsis;
      overflow: hidden;
      width: 130px;
    }
  }
}


@media (min-width: 640px) {
  .blog-card {
    flex-direction: row;
    max-width: 700px;
    /* max-height: 140px; */
  }
  .blog-card .meta {
    flex-basis: 50%;
    height: auto;
  }
  .blog-card .description {
    flex-basis: 60%;
  }
}
</style>
