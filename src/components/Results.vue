<template>
   <p>Reaction Time: <span class="score">{{ score }} </span> ms</p> 
   <p class="rank"> {{ rank }}</p>
   <p v-if="missingRank">You Missed First Position By {{ missingRank }} ms</p>
   <img :src="rankImage" alt="Rank Image" class="rankImage" />
</template>

<script>
import ninjaFingersImg from '@/assets/ninja.png';
import rapidReflexesImg from '@/assets/reflex.png';
import snailPaceImg from '@/assets/snail.png';

export default {
  props: ['score'],
  data() {
    return {
      rank: null,
      rankImage: null,
      missingRank: null
    }
  },
  mounted() {
    if (this.score < 250) {
      this.rank = "Ninja Fingers"
      this.rankImage = ninjaFingersImg
      
    } else if (this.score < 400) {
      this.rank = "Rapid Reflexes"
      this.rankImage = rapidReflexesImg
      this.missingRank = this.score - 250
    } else {
      this.rank = "Snail Pace..."
      this.rankImage = snailPaceImg
      this.missingRank = this.score - 250
    }
  }
}
</script>

<style>
.rank {
  font-size: 1.4em;
  color: #0faf87;
  font-weight: bold;
}
span.score {
    font-size: 30px;
    color: #bd0d0d;
    font-weight: bolder;
}
img.rankImage {
    width: 300px;
}
</style>