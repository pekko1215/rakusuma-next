<template>
  <v-app>
    <v-navigation-drawer fixed app> </v-navigation-drawer>
    <v-app-bar
      fixed
      elevation="1"
      app
      class="header-bar"
      height="30"
      clipped-right
    >
      <div class="header-wrapper">
        <span class="notification">
          <v-icon>mdi-web-off</v-icon>

          インターネットなし
        </span>
        <span class="clock-text">{{ clockString }}</span>
        <v-icon>mdi-battery-90</v-icon>
      </div>
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script lang="ts">
import { Vue, Component } from "nuxt-property-decorator";

@Component({})
export default class DefaultLayout extends Vue {
  time = new Date();
  timerInterval = -1;

  created() {
    this.timerInterval = window.setInterval(() => {
      this.time = new Date();
    }, 3000);
  }

  destroyed() {
    window.clearInterval(this.timerInterval);
  }

  get clockString() {
    const DayString = ["日", "月", "火", "水", "木", "金", "土"];
    return `${this.time.getMonth() + 1}月${this.time.getDate()}日(${
      DayString[this.time.getDay()]
    }) ${this.time.toTimeString().slice(0, 5)}`;
  }
}
</script>

<style scoped>
.theme--light.v-application {
  background-color: var(--v-background-base, #e6e2db) !important;
}

.theme--light.v-sheet {
  background-color: var(--v-background-base, #e6e2db) !important;
}

.header-bar .clock-text {
}

.header-bar .notification {
  flex: 1;
  font-size: 0.8rem;
}

.header-wrapper {
  font-size: 1.1em;
  font-weight: bold;
  width: 100%;
  display: flex;
  justify-content: flex-end;
  align-items: center;
}

.container {
  height: calc(100vh - 30px);
  overflow-y: hidden;
}
</style>
