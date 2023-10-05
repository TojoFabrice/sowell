<template v-if="workCount > 0">
  <tr>
    <td colspan="3">
      <div class="row no-wrap items-center">
        <div class="text-h6 q-ml-md">Publications</div>
      </div>
    </td>
  </tr>
  <template v-for="(work, i) in works" :key="work.id">
    <tr>
      <td class="text-left">Title</td>
      <td class="text-right">{{ work.title }}</td>
      <td class="text-right">
        <q-icon
          v-if="
            work.title !== null || work.title !== undefined || work.title !== ''
          "
          :name="work.title ? 'check' : 'error'"
          :color="work.title ? 'positive' : 'negative'"
          size="2em"
        ></q-icon>
      </td>
    </tr>
    <tr>
      <td class="text-left">Link</td>
      <td class="text-right">{{ work.link }}</td>
      <td class="text-right">
        <q-icon
          :name="isLinkValid(work.link) ? 'check' : 'error'"
          :color="isLinkValid(work.link) ? 'positive' : 'negative'"
          size="2em"
        ></q-icon>
      </td>
    </tr>
    <tr>
      <td class="text-left">Year</td>
      <td class="text-right">{{ work.year }}</td>
      <td class="text-right">
        <q-icon
          v-if="
            work.year.length == 4 || work.year !== undefined || work.year !== ''
          "
          :name="work.year ? 'check' : 'error'"
          :color="work.year ? 'positive' : 'negative'"
          size="2em"
        ></q-icon>
      </td>
    </tr>
    <tr v-if="i < workCount - 1">
      <td colspan="3"></td>
    </tr>
  </template>
</template>

<script lang="ts">
export default {
  props: {
    workCount: Number,
    works: Object,
  },
  methods: {
    isLinkValid(link: string) {
      const linkPattern =
        /^(http:\/\/|https:\/\/)(www\.)?[-a-zA-Z0-9@:%._\+~#=]{2,256}\.[a-z]{2,6}\b([-a-zA-Z0-9@:%_\+.~#?&//=]*)$/i;
      return linkPattern.test(link);
    },
  },
};
</script>
