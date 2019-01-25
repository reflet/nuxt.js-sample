<template>
  <section class="container">
    <div>
      <p>
        /users/{{userID}}
      </p>
    </div>
  </section>
</template>

<script>
  export default {
    name: "users-id",
    data() {
      return {
        userID: this.$route.params.id
      }
    }
  }
</script>
