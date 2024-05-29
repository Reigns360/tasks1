<template>
  <div>
    <h2>Task List</h2>
    <div>
        <ul>
        <li v-for="task in tasks" :key="task.id">
            {{ task.name }}
            <button @click="updateTask(task.id)">Update</button>
            <button @click="deleteTask(task.id)">Delete</button>
        </li>
        </ul>
    </div>
    <div>
        <input v-model="newTask" placeholder="New Task">
        <button @click="createTask">Add Task</button>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      tasks: [],
      newTask: ''
    }
  },
  methods: {
    async fetchTasks() {
      const response = await axios.get('http://localhost:8000/api/tasks/');
      this.tasks = response.data;
    },
    async createTask() {
      if (this.newTask) {
        await axios.post('http://localhost:8000/api/tasks/', { name: this.newTask });
        this.newTask = '';
        this.fetchTasks();
      }
    },
    async updateTask(id) {
      const newName = prompt('Enter new task name:');
      if (newName) {
        await axios.put(`http://localhost:8000/api/tasks/${id}/`, { name: newName });
        this.fetchTasks();
      }
    },
    async deleteTask(id) {
      await axios.delete(`http://localhost:8000/api/tasks/${id}/`);
      this.fetchTasks();
    }
  },
  mounted() {
    this.fetchTasks();
  }
}
</script>
