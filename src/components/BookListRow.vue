<template>
  <tr class="table-item__table-row">
    <td>{{ book.title }}</td>
    <td>{{ book.isbn }}</td>
    <td><BaseButton text="Add Bookmark" variant="secondary" /></td>
    <td>{{ book.price }}</td>
  </tr>
</template>

<script>
import BaseButton from "@/components/BaseButton.vue";
export default {
  components: {
    BaseButton,
  },
  props: {
    book: Object,
  },
};
</script>

<style scoped>
.table-item__table td {
  padding: 12px 15px;
}
</style>
