<template>
  <j-tray-plugin>
    <v-row>
      <j-docs-link :link="'https://jdaviz.readthedocs.io/en/'+vdocs+'/'+config+'/plugins.html#compass'">
        Show active data label, compass, and zoom box.
      </j-docs-link>
    </v-row>

    <plugin-viewer-select
      :items="viewer_items"
      :selected.sync="viewer_selected"
      label="Viewer"
      hint="Select a viewer to show."
    />

    <v-row v-if="data_label">
      <v-chip
        label=true
      >{{ data_label }}</v-chip>
    </v-row>

    <img class='invert-in-dark' v-if="img_data" :src="`data:image/png;base64,${img_data}`" style="width: 100%; max-width: 400px" />

  </j-tray-plugin>
</template>

<style>
.theme--dark .invert-in-dark {
  filter: brightness(0.88) invert(1);
}
</style>
