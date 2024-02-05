<template>
  <div>
    <TheHeader></TheHeader>
    <button @click="setSelectedComponent('ActiveGoals')"> Active Goals </button>
    <button @click="setSelectedComponent('ManagedGoals')"> Manage Goals </button>
    <!-- <ActiveGoals v-if="selectedComponent == 'ActiveGoals'"></ActiveGoals>
    <ManagedGoals v-if="selectedComponent == 'ManagedGoals'"></ManagedGoals> -->
    <keep-alive>
      <component :is="selectedComponent"></component>
    </keep-alive>

    <!-- <badge-list></badge-list>
    <user-info
      :full-name="activeUser.name"
      :info-text="activeUser.description"
      :role="activeUser.role"
    ></user-info>

    <CourseGoals>
      <template #default="slotProps">
        <h2>{{ slotProps.item }}</h2>
        <p>{{ slotProps.anotherProp }}</p>
      </template>
    </CourseGoals> -->
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
// import UserInfo from './components/UserInfo.vue';
// import BadgeList from './components/BadgeList.vue';
// import CourseGoals from './components/CourseGoals.vue';
import ActiveGoals from './components/ActiveGoals.vue';
import ManagedGoals from './components/ManagedGoals.vue';

export default {
  components: {
    TheHeader,
    // BadgeList,
    // UserInfo,
    // CourseGoals,
    ActiveGoals,
    ManagedGoals,
  },
  data() {
    return {
      selectedComponent: 'ActiveGoals',
      activeUser: {
        name: 'Erick Mutwiri',
        description: 'Site owner and admin',
        role: 'admin',
      },
    };
  },
  methods: {
    setSelectedComponent(cmp) {
      this.selectedComponent = cmp;
    }
  }
};
</script>

<style>
html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>