<template>
  <div class="v-sheet">
    <h1>Dashboard</h1>
  </div>
</template>

<script>
  import NameCard from '@/components/widgets/card/NameCard';
  import ProfileCard from '@/components/widgets/card/ProfileCard';
  import MessageList from '@/components/widgets/list/MessageList';
  import NotificationList from '@/components/widgets/list/NotificationList';
  import {Items as Users} from '@/api/user';
  import VWidget from '@/components/VWidget';

  export default {
    layout: "dashboard",
    name: "dashboard",
    components: {
      NameCard,
      ProfileCard,
      MessageList,
      NotificationList,
      VWidget
    },
    data() {
      return {
      };
    },
  };
</script>

<style lang="scss" scoped>
  .display-1 {
    color: $custom_blue !important;
    font-weight: 700 !important;   
  }
</style>
