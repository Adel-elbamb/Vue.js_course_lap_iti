<template>
  <div v-if="isOpen" class="modal">
    <div class="modal-content">
      <h3>Add New Student</h3>
      <label>ID:</label>
      <input v-model="newStudent.id" type="text" /><br />
      <label>Name:</label>
      <input v-model="newStudent.name" type="text" /><br />
      <label>City:</label>
      <input v-model="newStudent.city" type="text" /><br />
      <button @click="addStudent">OK</button>
      <button @click="$emit('close-modal')">Cancel</button>
    </div>
  </div>
</template>

<script>
export default {
  props: ["isOpen"],
  data() {
    return {
      newStudent: { id: "", name: "", city: "" },
    };
  },
  methods: {
    addStudent() {
      this.$emit("student-added", this.newStudent);
      this.newStudent = { id: "", name: "", city: "" }; 
    },
  },
};
</script>

<style>
.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}
.modal-content {
  background: white;
  padding: 20px;
  border-radius: 5px;
}

.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}

.modal-content {
  background: white;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
  width: 300px;
  text-align: center;
  animation: fadeIn 0.3s ease-in-out;
}

h3 {
  margin-bottom: 15px;
  font-size: 1.2rem;
}

label {
  display: block;
  margin: 10px 0 5px;
  font-weight: bold;
}

input {
  width: 100%;
  padding: 8px;
  margin-bottom: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

button {
  padding: 8px 15px;
  margin: 10px 5px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-weight: bold;
  transition: 0.3s ease-in-out;
}

button:first-of-type {
  background: #28a745;
  color: white;
}

button:first-of-type:hover {
  background: #218838;
}

button:last-of-type {
  background: #dc3545;
  color: white;
}

button:last-of-type:hover {
  background: #c82333;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: scale(0.9);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}

</style>
