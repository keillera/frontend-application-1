<template>
  <div class="area-search-user-card-list-container">
    <search-user-card v-for="user in users" :key="user.user_id" :user="user" />
  </div>
</template>

<script>
import SearchUserCard from '../organisms/SearchUserCard'

export default {
  components: {
    SearchUserCard
  },
  props: {
    users: {
      type: Array,
      required: true
    }
  }
}
</script>

<style lang="scss" scoped>
.area-search-user-card-list-container {
  display: grid;
  grid-area: search-user-card-list;
  grid-gap: 14px;
  grid-template-rows: repeat(auto-fill, auto);
}

@media screen and (max-width: 640px) {
  .area-search-user-card-list-container {
    grid-gap: 10px;
    grid-template-rows: repeat(auto-fill, auto);
  }
}

@media screen and (max-width: 320px) {
  .area-search-user-card-list-container {
    grid-template-columns: 300px;
  }
}
</style>
