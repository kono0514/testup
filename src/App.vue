<template>
  <v-app>
    <v-content>
      <W9Form/>
    </v-content>
  </v-app>
</template>

<script>
import W9Form from './components/W9Form';

export default {
  name: 'App',

  components: {
    W9Form,
  },

  data: () => ({
    //
  }),
};
</script>
