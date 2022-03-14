<template>
  <v-expansion-panels>
    <v-expansion-panel class="red darken-3">
      <v-expansion-panel-header class="white--text">
        Tryck här för snabbfakta om Fjärdhundra SK
      </v-expansion-panel-header>
      <v-expansion-panel-content>
        <v-list
      subheader
      two-line
    >
      <v-subheader inset>Folders</v-subheader>

      <v-list-item
        v-for="folder in folders"
        :key="folder.title"
      >
        <v-list-item-avatar>
          <v-icon
            class="grey lighten-1"
            dark
          >
            mdi-folder
          </v-icon>
        </v-list-item-avatar>

        <v-list-item-content>
          <v-list-item-title v-text="folder.title"></v-list-item-title>

          <v-list-item-subtitle v-text="folder.subtitle"></v-list-item-subtitle>
        </v-list-item-content>

        <v-list-item-action>
          <v-btn icon>
            <v-icon color="grey lighten-1">mdi-information</v-icon>
          </v-btn>
        </v-list-item-action>
      </v-list-item>

      <v-divider inset></v-divider>

      <v-subheader inset>Files</v-subheader>

      <v-list-item
        v-for="file in files"
        :key="file.title"
      >
        <v-list-item-avatar>
          <v-icon
            :class="file.color"
            dark
            v-text="file.icon"
          ></v-icon>
        </v-list-item-avatar>

        <v-list-item-content>
          <v-list-item-title v-text="file.title"></v-list-item-title>

          <v-list-item-subtitle v-text="file.subtitle"></v-list-item-subtitle>
        </v-list-item-content>

        <v-list-item-action>
          <v-btn icon>
            <v-icon color="grey lighten-1">mdi-information</v-icon>
          </v-btn>
        </v-list-item-action>
      </v-list-item>
    </v-list>
    <v-list>
      <v-list-item>
        <v-list-item-content>
          <v-banner
            two-line
        >
            <v-icon
            slot="icon"
            size="36"
            >
            mdi-note-text
            </v-icon>
            All fakturering och betalning sker via vår redovisningskonsult Marina Eklund Redovisning. Fjärdhundra SK c/o Marina Eklund Redovisning Långtora Lingonbacken 745 96 Enköping eller använd mailadressen info@fsk.nu
        </v-banner>
        </v-list-item-content>
      </v-list-item>
    </v-list>
      </v-expansion-panel-content>
    </v-expansion-panel>
  </v-expansion-panels>
</template>

<script>
  export default {
    data: () => ({
      files: [
        {
          color: 'red',
          icon: 'mdi-map-marker',
          subtitle: '745 96 Fjärdhundra',
          title: 'Långtora Lingonbacken',
        },
        {
          color: 'red',
          icon: 'mdi-phone',
          subtitle: '076-836 39 99',
          title: 'Telefon',
        },
        {
          color: 'red',
          icon: 'mdi-email',
          subtitle: 'info@fsk.nu',
          title: 'Epost',
        },
        {
          color: 'red',
          icon: 'mdi-numeric',
          subtitle: '817001-1285',
          title: 'Organisationsnummer',
        },
        {
          color: 'red',
          icon: 'mdi-cellphone-check',
          subtitle: '1234262440',
          title: 'Swish',
        },
        {
          color: 'red',
          icon: 'mdi-bank',
          subtitle: '501039-2',
          title: 'Kontonummer',
        },

      ],
      folders: [
        {
          subtitle: 'Jan 9, 2014',
          title: 'Photos',
        },
        {
          subtitle: 'Jan 17, 2014',
          title: 'Recipes',
        },
        {
          subtitle: 'Jan 28, 2014',
          title: 'Work',
        },
      ],
    }),
  }
</script>
<style>

</style>