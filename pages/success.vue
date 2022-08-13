<template>
  <div class="container">
    <p>成功しました！</p>
  </div>
</template>

<script>
export default {
  methods: {
    submit() {
      const db = this.$firebase.firestore();
      db.collection("user")
        .add({ name: "hoge" })
        .then(() => {
          console.log("成功");
        })
        .catch((e) => {
          console.log(e.message);
        });
    },
  },
};
</script>