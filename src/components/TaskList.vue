<template>
    <div>
      <h1>Task List</h1>
      <ul>
        <li v-for="task in tasks" :key="task.id">
          {{ task.title }} - {{ task.completed ? "Done" : "Pending" }}
          <button @click="deleteTask(task.id)">Delete</button>
        </li>
      </ul>
      <form @submit.prevent="addTask">
        <input v-model="newTaskTitle" placeholder="New Task Title" />
        <textarea v-model="newTaskDescription" placeholder="Task Description"></textarea>
        <button type="submit" class="add-task-btn">Add Task</button>
      </form>
    </div>
  </template>
  
  <script>
import axios from 'axios';

export default {
  data() {
    return {
      tasks: [],
      newTaskTitle: '',
      newTaskDescription: '',
    };
  },
  created() {
    this.fetchTasks();
  },
  methods: {
    fetchTasks() {
      // Update this line with the full URL for the API
      axios.get('http://127.0.0.1:8000/api/tasks/')
        .then(response => {
          this.tasks = response.data;
        })
        .catch(error => {
          console.error("There was an error fetching tasks:", error);
        });
    },
    addTask() {
      // Update this line with the full URL for the API
      axios.post('http://127.0.0.1:8000/api/tasks/', {
        title: this.newTaskTitle,
        description: this.newTaskDescription,
        completed: false
      }).then(() => {
        this.newTaskTitle = '';
        this.newTaskDescription = '';
        this.fetchTasks();
      }).catch(error => {
        console.error("There was an error adding the task:", error);
      });
    },
    deleteTask(id) {
      // Update this line with the full URL for the API
      axios.delete(`http://127.0.0.1:8000/api/tasks/${id}/`).then(() => {
        this.fetchTasks();
      }).catch(error => {
        console.error("There was an error deleting the task:", error);
      });
    }
  }
};
</script>

  
  <style scoped>
  /* Center the content */
  div {
    max-width: 600px;
    margin: 0 auto;
    padding: 20px;
    font-family: Arial, sans-serif;
  }
  
  h1 {
    text-align: center;
    color: #333;
  }
  
  /* Task list styles */
  ul {
    list-style: none;
    padding: 0;
  }
  
  li {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px;
    margin: 10px 0;
    border: 1px solid #ddd;
    border-radius: 5px;
    background-color: #f9f9f9;
  }
  
  /* Button styling */
  button {
    background-color: #ff5757;
    border: none;
    color: white;
    padding: 6px 12px;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s;
  }
  
  button:hover {
    background-color: #e04a4a;
  }
  
  /* Form styles */
  form {
    display: flex;
    flex-direction: column;
    gap: 10px;
    margin-top: 20px;
  }
  
  input, textarea {
    padding: 10px;
    font-size: 16px;
    border: 1px solid #ddd;
    border-radius: 5px;
    resize: none;
  }
  
  input {
    height: 40px;
  }
  
  textarea {
    height: 80px;
  }
  
  .add-task-btn {
    background-color: #4caf50;
    border: none;
    color: white;
    padding: 10px;
    font-size: 16px;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s;
  }
  
  .add-task-btn:hover {
    background-color: #45a049;
  }
  </style>
  