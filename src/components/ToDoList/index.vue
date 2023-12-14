<template>
<div class="container">
    <h1 class="text-center mt-5"> My Vue Todo APP </h1>
    <div class="d-flex">

        <input v-model="task" class="form-control" type="text" placeholder="Enter todo work" />
        <button type="button" @click="buttonSubmit" class="btn btn-warning round-0">Submit</button>
    </div>

    <table class="table table-bordered mt-5">
        <thead>
            <tr>
            <th scope="col"> Task</th>
            <th scope="col"> Status</th>
            <th scope="col"> #</th>
            <th scope="col"> #</th>
            </tr>
        </thead>
        <tbody>

            <tr v-for="(task, index) in tasks" :key="index">
                <td>{{ task.name }}</td>
                <td><span class="pointer" v-on:click="changeStatus(index)">{{ task.status }}</span> </td>
                <!-- <button v-on:click="changeStatus()"> {{ this.myStatus[counter]}} </button></td> -->
                <td> <button v-on:click="editRow(index)">Edit</button></td>
                <td> <button v-on:click="deleteRow(index)"> Delete</button></td>

            </tr>
        </tbody>
    </table>
</div>
</template>

<script>
export default {
    name: "ToDoList",
    data() {
        return {

            tasks: [{
                    name: "Add New Task upper",
                    status: "To-Do"
                },

            ],
            task: '',
            availableStatuses: ['To-Do', 'In-Progess', 'Finished'],
            counter: 0,
            editTask: null,
        };
    },
    methods: {

        buttonSubmit() {
            if (this.task.length === 0) return 0;
            if (this.editTask === null) {
                this.tasks.push({
                    name: this.task,
                    status: this.availableStatuses[0]
                });
            } else {
                this.tasks[this.editTask].name = this.task;
                this.editTask = null;
            }
            this.task = '';
        },
        changeStatus(index) {
            let newIndex = this.availableStatuses.indexOf(this.tasks[index].status)
            if (++newIndex > 2) newIndex = 0;

            this.tasks[index].status = this.availableStatuses[newIndex];

        },
        editRow(index) {
            this.task = this.tasks[index].name;
            this.editTask = index;
        },
        deleteRow(index) {
            this.tasks.splice(index, 1);

        }

    },
};
</script>

<style>
.pointer {
    cursor: pointer;
}
</style>
