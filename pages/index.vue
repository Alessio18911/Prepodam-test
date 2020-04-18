<template>
  <div>
    <HeaderBlock />
    <Programs />
  </div>
</template>

<script>
import "@/assets/styles/global.scss";
import HeaderBlock from '@/components/HeaderBlock';
import Programs from '@/components/Programs';

export default {
  components: {
    HeaderBlock,
    Programs
  }
};
</script>
