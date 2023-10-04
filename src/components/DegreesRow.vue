<template v-if="degrees.length">
  <tr>
    <td colspan="3">
      <div class="row no-wrap items-center">
        <div class="text-h6 q-ml-md">Degrees</div>
      </div>
    </td>
  </tr>
  <template v-for="(degree, i) in degrees" :key="degree.id">
    <tr>
      <td class="text-left">Title</td>
      <td class="text-right">{{ degree.title }}</td>
      <td class="text-right">
        <q-icon name="check" color="positive" size="2em"></q-icon>
      </td>
    </tr>
    <tr>
      <td class="text-left">Field</td>
      <td class="text-right">{{ degree.field }}</td>
      <td class="text-right">
        <q-icon name="check" color="positive" size="2em"></q-icon>
      </td>
    </tr>
    <tr>
      <td class="text-left">Year</td>
      <td class="text-right">{{ degree.year }}</td>
      <td class="text-right">
        <q-icon name="check" color="positive" size="2em"></q-icon>
      </td>
    </tr>
    <tr>
      <td class="text-left">Details</td>
      <td class="text-right">{{ degree.details }}</td>
      <td class="text-right">
        <q-icon name="check" color="positive" size="2em"></q-icon>
      </td>
    </tr>
    <tr v-if="i < degrees.length">
      <td colspan="3"></td>
    </tr>
  </template>
</template>
<script>
export default {
  props: {
    degrees: Object,
  },
};
</script>
