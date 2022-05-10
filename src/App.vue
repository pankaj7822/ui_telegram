<template>
  <v-app>
    <v-main>
      <Sender/>
    </v-main>
  </v-app>
</template>

<script>
import Sender from '@/components/Sender';

export default {
  name: 'App',

  components: {
    Sender,
  },

  data: () => ({
    //
  }),
};
</script>
