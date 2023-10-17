<script>

export default {
  data: () => {
      return {
        href: window.location.host + window.location.pathname
      };
  },
}



</script>

<template>
<a :href="href">{{ href }}</a>
</template>
