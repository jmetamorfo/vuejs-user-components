<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Many Details</p>
        <p>User name: {{ switchName() }}</p>
        <button @click="resetName">Reset name</button>
        <button @click="resetFn()">Reset by callback</button>
    </div>
</template>

<script>
  export default {
      props: {
        myName: {
          type: String,
          default: 'secret'
        },
        resetFn: Function
      },
      methods: {
        switchName() {
          return this.myName.split("").reverse().join("");
        },
        resetName() {
          this.myName = 'Juan';
          this.$emit('nameWasReset', this.myName);
        }
      }
  }
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>
