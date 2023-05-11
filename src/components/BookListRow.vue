<template>
  <tr class="table-item__table-row">
    <td>{{ title }}</td>
    <td>{{ isbn }}</td>
    <td>
      <BaseButton
        :text="buttonText"
        variant="secondary"
        @button-click="onBookmarkButtonClick"
      />
    </td>
  </tr>
</template>

<script>
import BaseButton from "@/components/BaseButton.vue";

export default {
  emits: ["bookmark-button-click"],
  components: {
    BaseButton,
  },
  props: {
    title: { type: String },
    isbn: { type: String },
    isBookmarked: { type: Boolean },
  },
  methods: {
    onBookmarkButtonClick() {
      this.$emit("bookmark-button-click");
    },
  },
  computed: {
    buttonText() {
      if (this.isBookmarked) {
        return "Remove Bookmark";
      } else {
        return "Add Bookmark";
      }
    },
  },
};
</script>

<style scoped>
.table-item__table th {
  padding: 12px 15px;
}
</style>
