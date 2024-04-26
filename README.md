# zadacha2
<template>
  <v-alert :value="show" :type="type" dismissible @input="closeNotification">
    {{ message }}
  </v-alert>
</template>

<script>
export default {
  props: {
    message: {
      type: String,
      required: true
    },
    type: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      show: true
    };
  },
  methods: {
    closeNotification() {
      this.show = false;
    }
  }
};
</script>


Пример использования компонента в родительском компоненте:

<template>
  <div>
    <h1>Parent Component</h1>

    <Notification message="This is an informational notification" type="info" />
    <Notification message="An error occurred" type="error" />
    <Notification message="Operation was successful" type="success" />
  </div>
</template>

<script>
import Notification from '@/components/Notification.vue';

export default {
  components: {
    Notification
  }
};
</script>
