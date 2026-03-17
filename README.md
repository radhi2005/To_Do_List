# Ex03 To-Do List using JavaScript
## Date:21-02-2026

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
### index.html
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>To-Do App</title>

  <!-- LINK CSS FILE -->
  <link rel="stylesheet" href="style.css">
</head>

<body>

  <div class="container">
    <h1>To-Do App</h1>

    <div class="input-section">
      <input type="text" id="taskInput" placeholder="Enter a task">
      <button id="addBtn">Add</button>
    </div>

    <ul id="taskList"></ul>
  </div>

  <!-- LINK JS FILE -->
  <script src="script.js"></script>

</body>
</html>
```

### Style.css
```
body {
  font-family: Arial;
  background: #f4f4f4;
  display: flex;
  justify-content: center;
  margin-top: 50px;
}

.container {
  background: white;
  padding: 20px;
  width: 300px;
  border-radius: 10px;
}

.input-section {
  display: flex;
  gap: 10px;
}

input {
  flex: 1;
  padding: 8px;
}

button {
  padding: 8px;
  cursor: pointer;
}

li {
  list-style: none;
  padding: 10px;
  margin-top: 10px;
  background: #eee;
  display: flex;
  justify-content: space-between;
}

.completed {
  text-decoration: line-through;
  color: gray;
}
```
### script.js
```
const input = document.getElementById("taskInput");
const addBtn = document.getElementById("addBtn");
const list = document.getElementById("taskList");

// Load saved tasks
function loadTasks() {
  list.innerHTML = localStorage.getItem("tasks") || "";
}
loadTasks();

// Add task
addBtn.addEventListener("click", function () {
  if (input.value === "") return;

  const li = document.createElement("li");
  li.textContent = input.value;

  // Mark complete
  li.addEventListener("click", function () {
    li.classList.toggle("completed");
    saveTasks();
  });

  // Delete button
  const delBtn = document.createElement("button");
  delBtn.textContent = "X";

  delBtn.addEventListener("click", function (e) {
    e.stopPropagation();
    li.remove();
    saveTasks();
  });

  li.appendChild(delBtn);
  list.appendChild(li);

  saveTasks();
  input.value = "";
});

// Save tasks
function saveTasks() {
  localStorage.setItem("tasks", list.innerHTML);
}
```
## OUTPUT
<img width="1797" height="787" alt="image" src="https://github.com/user-attachments/assets/cfce9f47-c770-44bf-82b8-b8a431b1eab4" />


## RESULT
The program for creating To-do list using JavaScript is executed successfully.
