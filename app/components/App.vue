<template>
  <Page>
    <StackLayout horizontalAlignment="center">
      <ActivityIndicator :busy="isBusy"></ActivityIndicator>
      <Wish v-if="!isBusy" @grant-wish="grantWish($event)" />
    </StackLayout>
  </Page>
</template>

<script lang="ts">
import { Component, Prop, Ref, Vue } from 'vue-property-decorator';
import { ActivityIndicator } from 'tns-core-modules/ui/activity-indicator';
import { EventData } from 'tns-core-modules/data/observable';
import Wish from './Wish';

@Component({
  components: { Wish },
})
export default class App extends Vue {
  isBusy: boolean = false;

  grantWish(args: EventData) {
    this.isBusy = true;

    // do something
  }
}
</script>

<style scoped></style>
