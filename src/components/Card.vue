<!--
This is a reusable component that is styled to show content as cards with title, content,
and description.

In order to make this component more generic and easy to personalize, there are slots on
each of the 3 main areas to show content: tile, content, and description. This allows the
developers to add content according to their will, not matter what they need. In this case, 
the component Cards is not limited by the props, considering there can be any content inside
each slot. 
-->

<template>
  <div class="card">
    <div class="title">
      <slot name="title" />
    </div>

    <div class="content">
      <slot name="content" />
    </div>

    <div class="description">
      <slot name="description" />
    </div>
  </div>
</template>

<script>
export default {
}
</script>

<style scoped>
.card {
  border: 1px solid silver;
  border-radius: 8px;
  max-width: 200px;
  margin: 0 5px;
  cursor: pointer;
  box-shadow: 0px 1px 3px darkgrey;
  transition: 0.2s;
}
.title, .content, .description {
  padding: 16px;
  text-transform: capitalize;
  text-align: center;
}
.title, .content {
  border-bottom: 1px solid silver;
}
.title {
  font-size: 1.25em;
}
.card:hover {
  transition: 0.2s;
  box-shadow: 0px 1px 9px darkgrey;
}
</style>
