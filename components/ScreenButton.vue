<template>
  <div class="screen-button">
    <v-btn
      elevation="2"
      v-bind="$attrs"
      class="pa-0"
      color="rgba(0,0,0,0)"
      width="100%"
      height="100%"
    >
      <div class="button-wrap">
        <div class="icon-area">
          <slot name="icon">
            <v-icon :size="iconSize" :color="iconColor">{{ icon }}</v-icon>
          </slot>
        </div>
        <div class="text-area">
          <span>{{ text }}</span>
        </div>
      </div>
    </v-btn>
  </div>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "nuxt-property-decorator";

@Component({})
export default class DefaultLayout extends Vue {
  @Prop({ default: "mdi-shape" })
  icon!: string;

  @Prop({ default: "" })
  text!: string;

  @Prop({ default: 70 })
  iconSize!: number;

  @Prop()
  iconColor?: string;
}
</script>

<style scoped>
.screen-button {
  padding: 5px;
  box-sizing: border-box;
}

.v-btn {
  font-size: 1.2em;
  font-weight: bold;
  flex-direction: column;
  flex-wrap: wrap;
  text-align: center;
}

.button-wrap {
  flex-direction: column;
  flex-wrap: wrap;
}

.icon-area {
}
.text-area {
  transform: scaleY(1.1);
}
</style>
