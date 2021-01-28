<template>
  <div class="about">
    <h1>This is my Playground page</h1>
    <b-container>
      <b-card-group
        v-for="(cardRow, index) in this.cardRowData"
        deck class="mt-3"
        align="left"
        :key="cardRow[index]"
      >
        <b-card v-for="card in cardRow"
          border-variant="primary"
          :key="card._id"
          :header="card.name"
          header-bg-variant="primary"
          header-text-variant="white">
            <b-card-body>
              <b-card-text>{{card.address}}</b-card-text>
              <b-card-text>{{card.age}} yo - SEX: {{card.gender}} - EYES:  {{card.eyeColor}}</b-card-text>
              <b-card-text>{{card.balance}}</b-card-text>
              <b-card-text>{{card.company}}</b-card-text>
              <b-card-text>{{card.phone}}</b-card-text>
            </b-card-body>
        </b-card>
      </b-card-group>
    </b-container>
  </div>
</template>

<script>
import sampleCards from '@/helpers/_cardsSample'
import _ from 'lodash';

export default {
  data(){
    return {
      sampleData: null,
    }
  },
  mounted() {
    //populates the component data with sample data
    this.sampleData = sampleCards
  },
  computed: {
    cardRowData(){
      return _.chunk(this.sampleData, 4)
    }
  }

}
</script>


