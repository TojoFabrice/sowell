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
      <q-icon
        :name="checkIconName(english)"
        :color="checkIconColor(english)"
        size="2em"
      ></q-icon>
    </td>
  </tr>
  <tr>
    <td class="text-left">French proficiency</td>
    <td class="text-right">{{ french }}</td>
    <td class="text-right">
      <q-icon
        :name="checkIconName(french)"
        :color="checkIconColor(french)"
        size="2em"
      ></q-icon>
    </td>
  </tr>
  <tr>
    <td class="text-left">German proficiency</td>
    <td class="text-right">{{ german }}</td>
    <td class="text-right">
      <q-icon
        :name="checkIconName(german)"
        :color="checkIconColor(german)"
        size="2em"
      ></q-icon>
    </td>
  </tr>
</template>

<script>
export default {
  props: {
    english: {
      type: Number,
      required: true,
    },
    french: {
      type: Number,
      required: true,
    },
    german: {
      type: Number,
      required: true,
    },
  },
  methods: {
    checkIconName(value) {
      return this.isPositive(value) ? 'check' : 'error';
    },
    checkIconColor(value) {
      return this.isPositive(value) ? 'positive' : 'negative';
    },
    isPositive(value) {
      return !isNaN(parseFloat(value)) && parseFloat(value) > 0;
    },
  },
};
</script>
