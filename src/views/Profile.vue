<template>
    <div>
        <books-by-genre></books-by-genre>
    </div>
</template>
<script>
import BooksByGenre from "./components/BooksByGenre";

export default {
  name: "components",
  components: {
    BooksByGenre,
  }
};
</script>
