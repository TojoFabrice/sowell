<template>
  <tr>
    <td class="text-left">Firstname</td>
    <td class="text-right">{{ firstname }}</td>
    <td class="text-right">
      <!-- <q-icon name="check" color="positive" size="2em"></q-icon> -->
      <q-icon
        v-if="firstname !== null || firstname !== undefined || firstname !== ''"
        :name="firstname ? 'check' : 'error'"
        :color="firstname ? 'positive' : 'negative'"
        size="2em"
      ></q-icon>
    </td>
  </tr>
  <tr>
    <td class="text-left">Lastname</td>
    <td class="text-right">{{ lastname }}</td>
    <td class="text-right">
      <q-icon name="check" color="positive" size="2em"></q-icon>
    </td>
  </tr>
  <tr>
    <td class="text-left">Birthdate</td>
    <td class="text-right">{{ birthdate }}</td>
    <td class="text-right">
      <q-icon
        v-if="isBirthdateValid"
        name="check"
        color="positive"
        size="2em"
      ></q-icon>
      <q-icon v-else name="error" color="negative" size="2em"></q-icon>
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
import { isValid, parseISO } from 'date-fns';

export default {
  props: {
    firstname: String,
    lastname: String,
    birthdate: {
      type: String,
      required: true,
    },
    bio: String,
  },
  computed: {
    isBirthdateValid() {
      // Vérifier si birthdate est ni null ni vide
      if (
        !this.birthdate ||
        this.birthdate == undefined ||
        this.birthdate.trim() === ''
      ) {
        return false;
      }

      // convertir le format "YYYY/MM/DD" en ISO 8601
      const parts = this.birthdate.split('/');
      if (parts.length === 3) {
        const isoDate = `${parts[0]}-${parts[1].padStart(
          2,
          '0'
        )}-${parts[2].padStart(2, '0')}`;

        // parser la date et vérifiez si elle est valide
        const parsedDate = parseISO(isoDate);
        return isValid(parsedDate);
      } else {
        return false;
      }
    },
  },
};
</script>
