<template>
  <div v-if="!isLoading">
    <q-list v-for="user in users" :key="user.id">
      <q-item>
        <q-item-section>
          <q-item-label>{{
            user.name + ' (' + user.username + ')'
          }}</q-item-label>
          <q-item-label side>{{}}</q-item-label>
          <q-item-label caption>{{ user.email }}</q-item-label>
        </q-item-section>
      </q-item>
      <q-separator inset />
    </q-list>
  </div>
  <div v-else class="spinner">
    <q-spinner size="100px" class=""></q-spinner>
  </div>
</template>

<script>
import axios from 'axios';
import { Notify } from 'quasar';

export default {
  data() {
    return {
      isLoading: true,
      users: [],
    };
  },
  mounted() {
    this.fetchUsers();
  },
  methods: {
    async fetchUsers() {
      try {
        const response = await axios.get(
          'https://jsonplaceholder.typicode.com/users'
        );
        this.users = response.data;
        console.log('789', this.users);
        this.isLoading = false;
      } catch (error) {
        console.error(
          'Erreur lors de la récupération des utilisateurs :',
          error
        );
        this.isLoading = false;
        Notify.create({
          type: 'negative',
          message: 'An error occurred while fetching users.',
        });
      }
    },
  },
};
</script>

<style>
.spinner {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 50vh;
}
</style>
