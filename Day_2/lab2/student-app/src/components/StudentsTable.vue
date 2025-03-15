<template>
  <div>
    <h2>Open Source</h2>
    <button @click="$emit('open-modal')">Add</button>
    <table border="1">
      <thead>
        <tr>
          <th>ID</th>
          <th>Name</th>
          <th>City</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="student in students" :key="student.id">
          <td>{{ student.id }}</td>
          <td>{{ student.name }}</td>
          <td>{{ student.city }}</td>
        </tr>
      </tbody>
    </table>
    
  </div>
</template>

<script>
export default {
  props: ["students"],
};
</script>

<style>
  div {
  text-align: center;
  margin-top: 20px;
}

h2 {
  font-size: 1.5rem;
  margin-bottom: 15px;
}

button {
  background: #007bff;
  color: white;
  padding: 8px 15px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-weight: bold;
  transition: 0.3s ease-in-out;
  margin-bottom: 15px;
}

button:hover {
  background: #0056b3;
}

table {
  width: 80%;
  margin: 0 auto;
  border-collapse: collapse;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  background: white;
}

th, td {
  padding: 10px;
  border: 1px solid #ddd;
  text-align: center;
}

th {
  background: #007bff;
  color: white;
  font-weight: bold;
}

tbody tr:nth-child(even) {
  background: #f2f2f2;
}

tbody tr:hover {
  background: #d6e4ff;
  transition: 0.3s ease-in-out;
}

</style>
