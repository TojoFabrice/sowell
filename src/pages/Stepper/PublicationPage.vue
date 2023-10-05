<template>
  <q-form>
    <template v-for="work in form.published_works" :key="work.id">
      <div class="column q-gutter-y-sm">
        <q-input outlined label="Title" v-model="work.title">
          <template v-slot:prepend>
            <q-icon name="book" />
          </template>
        </q-input>
        <q-input
          outlined
          label="Field"
          v-model="work.link"
          :class="{ 'is-invalid': !isLinkValid(work.link) }"
        >
          <template v-slot:prepend>
            <q-icon name="link" />
          </template>
        </q-input>
        <div
          class="validation-message"
          v-if="!isLinkValid(work.link) && work.link !== ''"
        >
          Invalid link. Please enter a valid HTTP or HTTPS link.
        </div>
        <q-input
          label="Year"
          v-model.number="work.year"
          type="number"
          :rules="[
            (val) => (val >= 1923 && val < 2023) || 'Please type a valid year',
          ]"
          outlined
        >
          <template v-slot:prepend>
            <q-icon name="calendar_month" />
          </template>
        </q-input>
      </div>
      <q-separator class="q-mb-md"></q-separator>
    </template>
  </q-form>
</template>
<script setup lang="ts">
import { useFormStore } from 'src/stores/form-store';
const { form } = useFormStore();

const isLinkValid = (link: string) => {
  const linkPattern =
    /^(http:\/\/|https:\/\/)(www\.)?[-a-zA-Z0-9@:%._\+~#=]{2,256}\.[a-z]{2,6}\b([-a-zA-Z0-9@:%_\+.~#?&//=]*)$/i;
  return linkPattern.test(link);
};
</script>

<style>
.is-invalid {
  border-color: red !important;
}

.validation-message {
  color: red;
  margin-top: 5px;
}
</style>
