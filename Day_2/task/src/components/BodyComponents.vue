<template>
    <div>
        <!-- Listen for event emitted from AddComponent -->
        <AddComponent @addStudent="addStudent" />
        <table>
            <thead>
                <tr>
                    <th>ID</th>
                    <th>Name</th>
                    <th>City</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(student, index) in students" :key="index">
                    <td>{{ student.id }}</td>
                    <td>{{ student.name }}</td>
                    <td>{{ student.city }}</td>
                </tr>
            </tbody>
            <tfoot>
                <tr>
                    <th colspan="3">Total: {{ students.length }}</th>
                </tr>
            </tfoot>
        </table>
    </div>
</template>

<script>
import studentData from "../student.js";
import AddComponent from './components/AddComponent.vue';

export default {
    components: {
        AddComponent
    },
    data() {
        return {
            students: [...studentData]
        };
    },
    methods: {
        addStudent() {
            this.students.push({ id: this.students.length + 1, name: "Adel", city: "Cairo" });
        }
    }
};
</script>

<style scoped>
table {
    width: 100%;
    border-collapse: collapse;
    box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.2);
    background-color: #fff;
}

thead {
    background-color: #007bff;
    color: white;
}

th, td {
    border: 1px solid black;
    padding: 10px;
    text-align: center;
}

tbody tr:hover {
    background-color: #f1f1f1;
}

tfoot {
    background-color: #007bff;
    color: white;
    font-weight: bold;
}
</style>
