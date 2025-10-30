# TO-DO-LIST-APP
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>To-Do List App</title>
<style>
  body {
    font-family: Arial, sans-serif;
    background-color: #f4f7f8;
    padding: 20px;
    display: flex;
    justify-content: center;
  }
  .todo-container {
    background: white;
    padding: 20px;
    border-radius: 8px;
    width: 300px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);
  }
  h2 {
    text-align: center;
    color: #333;
  }
  input[type="text"] {
    width: 100%;
    padding: 8px;
    box-sizing: border-box;
    border: 2px solid #ddd;
    border-radius: 4px;
  }
  button {
    margin-top: 10px;
    width: 100%;
    background-color: #5c9ded;
    color: white;
    padding: 10px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
  }
  button:hover {
    background-color: #4a8cdb;
  }
  ul {
    list-style-type: none;
    padding-left: 0;
    margin-top: 20px;
  }
  li {
    background: #e3f0ff;
    margin: 5px 0;
    padding: 10px;
    border-radius: 4px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  li button {
    background-color: #ff6666;
    border: none;
    border-radius: 4px;
    padding: 4px 8px;
    cursor: pointer;
    color: white;
  }
</style>
</head>
<body>
<div class="todo-container">
  <h2>To-Do List</h2>
  <input type="text" id="taskInput" placeholder="Add new task" />
  <button onclick="addTask()">Add Task</button>
  <ul id="taskList"></ul>
</div>

<script>
  function addTask() {
    const taskInput = document.getElementById('taskInput');
    const task = taskInput.value.trim();

    if (task === "") {
      alert('Please enter a task');
      return;
    }

    const taskList = document.getElementById('taskList');
    const li = document.createElement('li');
    li.textContent = task;

    const deleteBtn = document.createElement('button');
    deleteBtn.textContent = 'Delete';
    deleteBtn.onclick = function () {
      taskList.removeChild(li);
    };

    li.appendChild(deleteBtn);
    taskList.appendChild(li);

    taskInput.value = '';
  }
</script>
</body>
</html>
