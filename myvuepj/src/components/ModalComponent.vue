<template>
  <div class="backdrop" @click.self="closeModal">
    <div
      :class="{
        dark: dark === true,
        light: dark === false,
      }"
    >
      <slot name="Dark" />
      <slot name="Light" />
    </div>
  </div>
</template>
        <!-- delete: themes === 'delete', -->
        <!-- success: themes === 'success',	 -->
        <!-- background-color: rgba(0, 0, 0, 0.5); 
        color: white; -->
<script>
export default {
  props: ["themes", "dark"],
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>
	
<style>
.backdrop {
  background-color: rgba(0, 0, 0, 0.445);
  position: fixed;
  top: 0;
  width: 100%;
  height: 100%;
  justify-content: center;
  align-items: center;
}
.modal {
  background-color: rgba(0, 0, 0, 0.5);
  color: white;
  padding: 20px;
  width: 80%;
  margin: 100px auto;
  border-radius: 10px;
}
.success {
  background-color: rgba(0, 190, 0, 0.589);
  color: white;
}
.delete {
  background-color: rgba(220, 20, 60, 0.493);
  color: white;
}

.dark {
  background-color: black;
  color: white;
  padding: 20px;
  width: 80%;
  margin: 100px auto;
  border-radius: 10px;
}
.light {
  background-color: white;
  color: black;
  padding: 20px;
  width: 80%;
  margin: 100px auto;
  border-radius: 10px;
}
</style>