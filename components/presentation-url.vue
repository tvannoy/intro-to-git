<script>

export default {
  data: () => {
      return {
        href: window.location.origin,
      };
  },
}



</script>

<template>
<a :href="href">{{ href }}</a>
</template>
