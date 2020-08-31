<template>
  <v-card>
    <v-card-title>
      Glossary
      <v-spacer />
      <v-text-field
        v-model="search"
        append-icon="mdi-magnify"
        label="Search"
        single-line
        hide-details
      />
    </v-card-title>
    <v-data-table
      :headers="headers"
      :items="glossaryList"
      :search="search"
    />
  </v-card>
</template>

<script>
  import * as glossaryJson from '../../data/glossary.json'
  export default {
    data: () => ({
      search: '',
      headers: [
        {
          text: 'Word',
          align: 'start',
          sortable: false,
          value: 'word',
        },
        { text: 'Additional Meaning', value: 'additionalMeaning' },
        { text: 'Common Usage If Component', value: 'commonUsageIfComponent' },
        { text: 'Definition', value: 'definition' },
        { text: 'Tags', value: 'tags' },
      ],
      glossaryList: glossaryJson,
    }),
  }

</script>
