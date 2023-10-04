<template>
  <q-markup-table flat bordered>
    <thead>
      <tr>
        <th colspan="3">
          <div class="row no-wrap items-center">
            <div class="text-h6 q-ml-md">Personal info</div>
          </div>
        </th>
      </tr>
      <tr>
        <th class="text-left" width="15%">Label</th>
        <th class="text-right" width="80%">Value</th>
        <th class="text-right" width="5%">Validity</th>
      </tr>
    </thead>
    <tbody>
      <PersonnalInfo
        :firstname="form.firstname"
        :lastname="form.lastname"
        :birthdate="form.birthdate"
        :bio="form.bio"
      />

      <ProfessionalInfo
        :english="form.professional.english"
        :french="form.professional.french"
        :german="form.professional.german"
      />

      <DegreesRow :degrees="form.professional.degrees" />

      <PublicationRow
        :workCount="form.published_works_count"
        :works="form.published_works"
      />
    </tbody>
  </q-markup-table>
</template>
<script setup lang="ts">
import { useFormStore } from 'src/stores/form-store';
import PersonnalInfo from 'src/components/PersonnalInfo.vue';
import ProfessionalInfo from 'src/components/ProfessionalInfo.vue';
import DegreesRow from 'src/components/DegreesRow.vue';
import PublicationRow from 'src/components/PublicationRow.vue';
const { form } = useFormStore();
</script>

<style>
td {
  max-width: 400px;
  overflow: scroll;
}
</style>
