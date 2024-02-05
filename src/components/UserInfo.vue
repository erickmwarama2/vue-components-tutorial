<template>
  <BaseCard>
    <template v-slot:header>
      <h3>{{ fullName }}</h3>
      <base-badge :type="role" :caption="role.toUpperCase()"></base-badge>
    </template>
    <p>{{ infoText }}</p>
  </BaseCard>
</template>

<script>
import BaseCard from './BaseCard.vue';

export default {
  props: ['fullName', 'infoText', 'role'],
  components: {
    BaseCard,
  }
};
</script>

<style>

section header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>