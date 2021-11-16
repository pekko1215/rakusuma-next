<template>
  <div class="container-2 pa-0">
    <div class="button-grid">
      <screen-button class="main" text="電話" icon="mdi-phone-outline" />
      <screen-button class="bt-1" text="メール" icon="mdi-email-outline" />
      <screen-button
        class="bt-2"
        text="インターネット"
        icon="mdi-web"
        disabled
      />
    </div>
    <div class="short-cut">
      <screen-button
        class="sc-1"
        icon-color="#cc0000"
        :icon-size="smallIconSize"
        text="ラクラク電話1"
        icon="mdi-numeric-1-box-outline"
      />
      <screen-button
        class="sc-2"
        icon-color="#00aa00"
        :icon-size="smallIconSize"
        text="ラクラク電話2"
        icon="mdi-numeric-2-box-outline"
      />
      <screen-button
        class="sc-3"
        icon-color="#0000cc"
        :icon-size="smallIconSize"
        text="ラクラク電話3"
        icon="mdi-numeric-3-box-outline"
      />
    </div>
    <div class="app-grid">
      <screen-button
        class="app-1"
        :icon-size="serviceIconSize"
        icon-color="#00acee"
        text="ツイッター"
        icon="mdi-twitter"
      />
      <screen-button
        class="app-2"
        icon-color="#7289da"
        :icon-size="serviceIconSize"
        text="ディスコード"
        icon="mdi-discord"
      />
      <screen-button
        class="app-3"
        icon-color="#FF0000"
        :icon-size="serviceIconSize"
        text="ユーチューブ"
        icon="mdi-youtube"
      />
      <screen-button
        class="app-4"
        icon-color="#1DB954"
        :icon-size="serviceIconSize"
        text="スポティファイ"
        icon="mdi-spotify"
      />
    </div>
    <div class="search-area">
      <v-text-field solo rounded>
        <template #prepend-inner>
          <v-icon>mdi-google</v-icon>
        </template>
        <template #append>
          <v-icon>mdi-microphone</v-icon>
        </template>
      </v-text-field>
    </div>
  </div>
</template>

<style scoped>
.button-grid {
  display: grid;
  grid-template:
    "main main bt-1 bt-1" 50%
    "main main bt-2 bt-2" 50% /
    25% 25% 25%;
  height: 40%;
}

.short-cut {
  display: grid;
  grid-template:
    "sc-1 sc-2 sc-3" 100% /
    auto auto auto;
  height: 15%;
}

.sc-1 {
  grid-area: sc-1;
}

.sc-2 {
  grid-area: sc-2;
}

.sc-3 {
  grid-area: sc-3;
}

.short-cut .screen-button {
  font-size: 0.7em !important;
}

.main {
  grid-area: main;
}

.bt-1 {
  grid-area: bt-1;
}

.bt-2 {
  grid-area: bt-2;
  font-size: 1.05em;
}

.app-grid {
  display: grid;
  grid-template:
    "app-1 app-1 app-2 app-2" 50%
    "app-3 app-3 app-4 app-4" 50% /
    25% 25% 25% 25%;
  height: 36%;
}

.app-1 {
  grid-area: app-1;
}

.app-2 {
  grid-area: app-2;
}

.app-3 {
  grid-area: app-3;
}

.app-4 {
  grid-area: app-4;
}

.search-area {
  padding: 5px;
  font-size: 1.2em;
}

.container-2 {
  height: 100%;
}
</style>

<script lang="ts">
import { Vue, Component, Prop } from "nuxt-property-decorator";

@Component({})
export default class IndexPage extends Vue {
  smallIconSize = 60;
  serviceIconSize = 56;
}
</script>
