<template>
  <sw-switch
    v-if="hasLabel"
    v-model:value="model"
    :class="css"
    :label="labelText"
    :big="big"
  />
  <sw-switch
    v-else
    v-model:value="model"
    :class="css"
    :big="big"
  />
</template>

<script lang="ts">
import { reactive, ref } from 'vue'
import SwSwitch from '@snowind/switch'

export default {
  components: {
    SwSwitch,
  },
  props: {
    labelText: {
      type: String,
      default: 'Label',
    },
    hasLabel: {
      type: Boolean,
      default: false,
    },
    big: {
      type: Boolean,
      default: false,
    },
    css: {
      type: String,
      default: '',
    },
    checked: {
      type: Boolean,
      default: true,
    },
  },

  setup(props: any) {
    props = reactive(props)
    const model = ref(props.checked)

    return {
      model,
    }
  },
}
</script>
