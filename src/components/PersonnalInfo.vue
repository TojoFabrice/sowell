<template>
  <tr>
    <td class="text-left">Firstname</td>
    <td class="text-right">{{ firstname }}</td>
    <td class="text-right">
      <q-icon name="check" color="positive" size="2em"></q-icon>
    </td>
  </tr>
  <tr>
    <td class="text-left">Lastname</td>
    <td class="text-right">{{ lastname }}</td>
    <td class="text-right">
      <q-icon name="error" color="negative" size="2em"></q-icon>
    </td>
  </tr>
  <tr>
    <td class="text-left">Birthdate</td>
    <td class="text-right">{{ birthdate }}</td>
    <td class="text-right">
      <q-icon name="check" color="positive" size="2em"></q-icon>
    </td>
  </tr>
  <tr>
    <td class="text-left">Bio</td>
    <td class="text-right">{{ bio }}</td>
    <td class="text-right">
      <q-icon name="check" color="positive" size="2em"></q-icon>
    </td>
  </tr>
</template>

<script>
export default {
  props: {
    firstname: String,
    lastname: String,
    birthdate: String,
    bio: String,
  },
};
</script>
