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
        <q-icon name="check" color="positive" size="2em"></q-icon>
      </td>
    </tr>
    <tr>
      <td class="text-left">Link</td>
      <td class="text-right">{{ work.link }}</td>
      <td class="text-right">
        <q-icon name="check" color="positive" size="2em"></q-icon>
      </td>
    </tr>
    <tr>
      <td class="text-left">Year</td>
      <td class="text-right">{{ work.year }}</td>
      <td class="text-right">
        <q-icon name="check" color="positive" size="2em"></q-icon>
      </td>
    </tr>
    <tr v-if="i < workCount - 1">
      <td colspan="3"></td>
    </tr>
  </template>
</template>

<script>
export default {
  props: {
    workCount: Number,
    works: Object,
  },
};
</script>
