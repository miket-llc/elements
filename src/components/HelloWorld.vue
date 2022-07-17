<script setup lang="ts">
import { ref } from 'vue'
import { Splitpanes, Pane } from 'splitpanes'
import 'splitpanes/dist/splitpanes.css'

defineProps<{ msg: string }>()
//let simplemde = new SimpleMDE();

const count = ref(0)
</script>
<template>
  <splitpanes horizontal :push-other-panes="true">
    <pane>
      <span>{{msg}}</span>
    </pane>
    <pane>
      <splitpanes :push-other-panes="true">
        <pane>
          <span>2</span>
        </pane>
        <pane>
          <span>3</span>
        </pane>
        <pane>
          <span>4</span>
        </pane>
      </splitpanes>
    </pane>
    <pane>
      <span>5</span>
    </pane>
  </splitpanes>
</template>
<style>
</style>
