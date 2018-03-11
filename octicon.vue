
<style>
.octicon {
  vertical-align: text-bottom !important;
}
</style>

<template>
  <span>
    <span v-html="svg"></span>
    <span v-if="label" class="sr-only">{{label}}</span>
  </span>
</template>

<script>
var octicons = require('octicons');

module.exports = {
  props: {
    name: {
      default: 'octoface'
    },

    label: {
      default: ''
    },
  },

  computed: {
    svg: function(){
      if(octicons[this.name] == null) {
        return octicons.octoface.toSVG();
      }
      return octicons[this.name].toSVG();
    },
  }
};
</script>
