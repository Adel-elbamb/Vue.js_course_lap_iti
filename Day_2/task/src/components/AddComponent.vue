<template>
    <div>
        <button class="bg-info w-100 my-3" @click="studentadd">Add</button>
    </div>
</template>

<script>
export default {
    methods: {
        studentadd() {
            this.$emit("addStudent"); // Emitting event to parent
        }
    }
};
</script>
