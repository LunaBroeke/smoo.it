<template><img
  class="smoo-role-icon"
  :src="require('@/assets/tag/' + $attrs.type + '.png')"
  alt="role icon"
/></template>
<script>export default { inheritAttrs: false }</script>
<style lang="scss">
img.smoo-role-icon {
  width: 1em;
  height: 1em;
  filter: brightness(0.15);
}
</style>
