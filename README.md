# MWAD-EX_03-To-Do-List-using-JavaScript
## Date: 08-09-2025

## AIM
To create a To-do Application with all features using JavaScript.

## ALGORITHM
### STEP 1
Build the HTML structure (index.html).

### STEP 2
Style the App (style.css).

### STEP 3
Plan the features the To-Do App should have.

### STEP 4
Create a To-do application using Javascript.

### STEP 5
Add functionalities.

### STEP 6
Test the App.

### STEP 7
Open the HTML file in a browser to check layout and functionality.

### STEP 8
Fix styling issues and refine content placement.

### STEP 9
Deploy the website.

### STEP 10
Upload to GitHub Pages for free hosting.

## PROGRAM
## index.html
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Simple To-Do App</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="app-container">
    <h2>To-Do Tasks</h2>
    <div class="input-wrapper">
      <input type="text" id="newTask" placeholder="Add a new task...">
      <button id="addTaskBtn">+</button>
    </div>
    <div class="tasks-list" id="tasksList"></div>
  </div>

  <footer>
    <p>Made by <b>JAYARAJ B 212223043002</b></p>
  </footer>

  <script src="script.js"></script>
</body>
</html>

```
## style.css
```
body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background-color: #f0f2f5;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 0;
  min-height: 100vh;
}

.app-container {
  background-color: #fff;
  width: 90%;
  max-width: 800px;
  padding: 30px 40px;
  margin-top: 50px;
  border-radius: 15px;
  box-shadow: 0 8px 20px rgba(0,0,0,0.2);
}

h2 {
  text-align: center;
  color: #333;
  margin-bottom: 25px;
  font-size: 2em;
}

.input-wrapper {
  display: flex;
  margin-bottom: 20px;
}

#newTask {
  flex: 1;
  padding: 15px 20px;
  border-radius: 10px 0 0 10px;
  border: 1px solid #ccc;
  outline: none;
  font-size: 1.1em;
}

#addTaskBtn {
  background-color: #ff7f50;
  color: white;
  border: none;
  padding: 0 25px;
  font-size: 1.5em;
  font-weight: bold;
  cursor: pointer;
  border-radius: 0 10px 10px 0;
  transition: background 0.3s ease;
}

#addTaskBtn:hover {
  background-color: #ff6347;
}

.tasks-list {
  max-height: 500px;
  overflow-y: auto;
}

.task-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #f7f7f7;
  margin-bottom: 15px;
  padding: 15px 20px;
  border-radius: 12px;
  cursor: pointer;
  transition: background 0.3s ease;
  font-size: 1.2em;
}

.task-item.completed {
  text-decoration: line-through;
  color: #999;
}

.task-item:hover {
  background-color: #e0e0e0;
}

.task-item button {
  background-color: #ff4d4d;
  border: none;
  color: white;
  padding: 6px 12px;
  border-radius: 8px;
  cursor: pointer;
  font-size: 1em;
  transition: background 0.3s ease;
}

.task-item button:hover {
  background-color: #cc0000;
}

footer {
  margin-top: auto;
  padding: 15px;
  font-size: 16px;
  color: #555;
  text-align: center;
}

```
## script.js
```
const taskInput = document.getElementById("newTask");
const addBtn = document.getElementById("addTaskBtn");
const tasksList = document.getElementById("tasksList");

window.onload = loadTasks;

addBtn.addEventListener("click", () => {
  const taskText = taskInput.value.trim();
  if (!taskText) return;
  addTask(taskText);
  taskInput.value = "";
});

function addTask(text, completed = false) {
  const taskDiv = document.createElement("div");
  taskDiv.className = "task-item";
  if (completed) taskDiv.classList.add("completed");
  taskDiv.textContent = text;

  const deleteBtn = document.createElement("button");
  deleteBtn.textContent = "Delete";
  deleteBtn.addEventListener("click", (e) => {
    e.stopPropagation();
    taskDiv.remove();
    saveTasks();
  });

  taskDiv.appendChild(deleteBtn);
  taskDiv.addEventListener("click", () => {
    taskDiv.classList.toggle("completed");
    saveTasks();
  });

  tasksList.appendChild(taskDiv);
  saveTasks();
}

function saveTasks() {
  const tasks = [];
  document.querySelectorAll(".task-item").forEach(task => {
    tasks.push({
      text: task.firstChild.textContent,
      completed: task.classList.contains("completed")
    });
  });
  localStorage.setItem("simpleTasks", JSON.stringify(tasks));
}

function loadTasks() {
  const tasks = JSON.parse(localStorage.getItem("simpleTasks")) || [];
  tasks.forEach(task => addTask(task.text, task.completed));
}
```
## OUTPUT
<img width="1917" height="1130" alt="Screenshot 2025-09-08 112721" src="https://github.com/user-attachments/assets/af6add33-347c-402c-9d85-e69cb102870f" />

## RESULT
The program for creating To-do list using JavaScript is executed successfully.

## RESULT
The program for creating To-do list using JavaScript is executed successfully.
