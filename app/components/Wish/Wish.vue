<template>
  <StackLayout>
    <TextField v-model="wish" hint="Make a wish..." />
    <Button
      v-if="wish !== ''"
      text="Grant my wish!"
      @tap="onTap($event)"
    ></Button>
  </StackLayout>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import { EventData } from 'tns-core-modules/data/observable';

@Component
export default class WishComponent extends Vue {
  wish: string = '';

  onTap(args: EventData) {
    this.$emit('grant-wish', args.object);
  }
}
</script>
