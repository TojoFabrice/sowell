<template>
  <tr>
    <td colspan="3">
      <div class="row no-wrap items-center">
        <div class="text-h6 q-ml-md">Professional info</div>
      </div>
    </td>
  </tr>
  <tr>
    <td class="text-left">English proficiency</td>
    <td class="text-right">{{ english }}</td>
    <td class="text-right">
      <q-icon name="check" color="positive" size="2em"></q-icon>
    </td>
  </tr>
  <tr>
    <td class="text-left">French proficiency</td>
    <td class="text-right">{{ french }}</td>
    <td class="text-right">
      <q-icon name="error" color="negative" size="2em"></q-icon>
    </td>
  </tr>
  <tr>
    <td class="text-left">German proficiency</td>
    <td class="text-right">{{ german }}</td>
    <td class="text-right">
      <q-icon name="check" color="positive" size="2em"></q-icon>
    </td>
  </tr>
</template>

<script>
export default {
  props: {
    english: String,
    french: String,
    german: String,
  },
};
</script>
