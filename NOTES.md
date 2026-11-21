# Week 1 Assessment: Starter App Exploration

## 1. Project Overview

The Task Tracker Starter App is an application that helps users create, manage, edit and delete tasks. Users can also set task priorities and due dates, mark tasks as completed, and filter tasks based on their completion status.

## 2. What I Discovered

### Frontend

The frontend is built with React and Vite. It is located in the `client` folder.

- `index.html`: Provides the HTML page that loads the application.
- `main.jsx`: The entry point of the React application. It renders the main App component.
- `App.jsx`: Contains the main application interface and task management functionality.
- `package.json`: Contains the frontend dependencies and scripts.
- `vite.config.js`: Contains the Vite configuration.
- `node_modules`: Contains the installed project dependencies.

### How the Frontend Works

The application uses React's `useState` to manage tasks, task names, priorities, due dates, filters and editing information.

It uses `useEffect` to fetch existing tasks when the application loads.

The frontend communicates with the backend through API requests:

- GET `/api/tasks` retrieves tasks.
- POST `/api/tasks` creates a new task.
- PUT `/api/tasks/:id` updates a task.
- DELETE `/api/tasks/:id` deletes a task.

### Application Features Tested

- Creating tasks works successfully.
- Each task has a unique ID that helps identify and distinguish it from other tasks.
- The `done` value is initially `0` when a task is not completed. When the task is marked as completed, the value changes to `1`.
- Editing task names works.
- Editing task priority and due dates is not available.
- Tasks can be created without a due date.
- Tasks remain available after refreshing the browser.
- Deleting tasks works, and the response displayed `ok: true`.
- Filtering tasks by All, Active and Done is available.
- Edit and Delete buttons remain visible even after a task is marked as completed.

### Backend

The project has a separate `server` workspace. The frontend sends API requests to the backend to create, retrieve, update and delete tasks.

The backend implementation still needs to be explored further to understand its internal structure and how it stores task information.

## 3. Three Improvements I Would Make

### Improvement 1: Improve Task Editing

I would allow users to edit task priority and due date in addition to the task name.

**Why:** This would give users more flexibility when task details, deadlines or priorities change.

### Improvement 2: Add Task Title Validation

I would prevent users from submitting tasks without entering a task name.

**Why:** This would ensure that every task has a meaningful title and prevent empty tasks from being added.

### Improvement 3: Improve Actions for Completed Tasks

I noticed that when a task is marked as completed, the Edit and Delete buttons remain visible.

I would improve how these buttons are displayed for completed tasks. For example, I would make completed tasks visually distinct and consider disabling the Edit option while keeping Delete available.

**Why:** This would make it clearer that a task has already been completed and help prevent accidental changes to completed tasks while still allowing users to remove them.

## 4. AI Tools and Prompts Used

**AI Tool:** ChatGPT

Prompts used:

1. Explain the purpose of the project's `package.json` file.
2. Explain how the frontend, backend and database work together in a Task Tracker application.
3. Explain the purpose of the files inside the client folder.
4. Explain what the React code in `main.jsx` does.
5. Explain what the code in `App.jsx` does and how its functions work.
6. Help me identify possible improvements to the Task Tracker application.

## 5. One Thing AI Got Wrong or Missed

During my exploration, AI suggested that the application might need clearer success and error messages. I checked how the application behaved and noticed that task operations responded immediately. For example, when I deleted a task, it disappeared immediately and the response showed `ok: true`.

This taught me that AI-generated explanations and suggestions should be verified against the actual application and its code rather than accepted without checking.