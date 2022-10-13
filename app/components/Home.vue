<template>
  <Page>
    <ActionBar>
      <Label text="Home" class="font-bold text-lg" />
    </ActionBar>

    <GridLayout>
      <Label
        class="text-xl align-middle text-center text-gray-500"
        :text="message"
        @tap="logMessage"
      />
      <Button @click="batLevel" :text="test" />
    </GridLayout>
  </Page>
</template>

<script lang="ts">
import Vue from 'nativescript-vue';

export default Vue.extend({
  computed: {
    message() {
      return 'Blank {N}-Vue app';
    },
  },

  methods: {
    logMessage() {
      console.log('You have tapped the message!');
    },
    batLevel() {
      let value = bm.getIntProperty(BatteryManager.BATTERY_PROPERTY_CAPACITY);
      alert(formatMessage(value));
    },
  },
  
});
</script>

<style>
/* .info {
    font-size: 20;
  } */
</style>
