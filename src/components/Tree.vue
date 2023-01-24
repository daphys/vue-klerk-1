<template>
  <div v-for="(request, id) in requestInfo.data" :key="id">
    {{ request }}
  </div>
</template>

<script>
export default {
  data() {
    return {
      isAllowEmpty: false,
      requestInfo: null,
    };
  },
  mounted() {
    this.axios
      .get("https://www.klerk.ru/yindex.php/v3/event/rubrics")
      .then((response) => {
        try {
          // сохраняем данные
          this.requestInfo = response;
        } catch (e) {
          console.error("text error:", e);
        }
      });
  },
};
</script>

<style></style>
