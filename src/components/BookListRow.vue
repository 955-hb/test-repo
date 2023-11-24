<template>
  <tr class="table-item__table-row">
    <td>{{ book.title }}</td>
    <td>{{ book.isbn }}</td>
    <td>
      <BaseButton
        @btn-click="onBookmarkBtnClick()"
        :text="buttonLabel"
        variant="secondary"
      />
    </td>
    <td>{{ book.price }}</td>
  </tr>
</template>

<script>
import BaseButton from "@/components/BaseButton.vue";
export default {
  components: {
    BaseButton,
  },
  emits: ["bookmark-change"],
  props: {
    book: Object,
  },
  computed: {
    buttonLabel() {
      return this.book.isBookmarked ? "remove bookmark" : "add bookmark";
    },
  },
  methods: {
    onBookmarkBtnClick() {
      this.$emit("bookmark-change", this.book);
    },
  },
};
</script>

<style scoped>
.table-item__table td {
  padding: 12px 15px;
}
</style>
