<template>
  <div class="pg-index" :style="{backgroundColor: '{{bgColor}}'}">
    <div class="main-container" :style="{
        backgroundColor: '{{bgColor}}',
        backgroundImage: '{{bgImage}}' ? 'url({{bgImage}})' : null,
        backgroundSize: '{{bgSize}}',
        backgroundRepeat: 'no-repeat'
      }">
      {{#components}}
      <div class="cp-module-editor {{className}} {{data.className}}">
        <{{name}} class="temp-component" :data="{{tostring data}}" data-type="{{upcasefirst name}}"></{{name}}>
    </div>
    {{/components}}
  </div>
  </div>
</template>

<script>
  {{#noRepeatCpsName}}
  import {{upcasefirst this}} from '{{this}}'
  {{/noRepeatCpsName}}
  export default {
      name: '{{upcasefirst repoName}}',
        components: {
        {{#noRepeatCpsName}}
        {{upcasefirst this}},
        {{/noRepeatCpsName}}
        }
        }
</script>
