<script>
import { RouterLink, RouterView } from 'vue-router'
import {computed, ref} from 'vue'
import Button from '../components/Button.vue';
import ChallengeCard from '@/components/ChallengeCard.vue';
import { useRouter } from 'vue-router';
import { challengesDescription } from '@/constants';

export default { 
    data(){
      return{
        items: challengesDescription,
      }
    },
    components:{
        Button,
        ChallengeCard
    },
};
</script>

<template>
  <div style="width: 100%;">
    <v-container
      class="mb-6"
      
    >
    
      <v-row
        align="start"
        no-gutters
        class="three-cols"
        style="height: 150px;"
      >
        <v-col v-for="challenge in items" :key="challenge">
          <v-sheet class="pa-2 ma-2">
            <ChallengeCard class="card" :title="challenge.title" :description="challenge.description" :Level="challenge.Level" :imageURL="challenge.imageURL"/>
          </v-sheet>
        </v-col>
      </v-row>

    </v-container>
  </div>
</template>

<style>
.three-cols {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
}

.card{
  transition: .2s ease-in-out;
  box-shadow: 3px 3px 19px 2px rgba(0,0,0,0.33);
}

.card:hover{
  box-shadow: 3px 3px 19px 2px rgba(0,0,0,1);
}
</style>