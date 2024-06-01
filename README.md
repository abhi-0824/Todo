# To-Do List Project

This project is a simple to-do list application built with Vite and React. The To-Do List component allows for task addition, removal, completion marking, dynamic task display, optional sorting, filtering, and localStorage integration.

## Table of Contents

1. [Setup](#setup)
2. [Unit Tests](#unit-tests)
    - [Task Addition](#task-addition)
    - [Task Removal](#task-removal)
    - [Completion Marking](#completion-marking)
    - [Validation](#validation)
3. [Integration Tests](#integration-tests)
    - [Dynamic Display](#dynamic-display)
    - [Sorting and Filtering](#sorting-and-filtering)
    - [LocalStorage Integration](#localstorage-integration)
4. [End-to-End Tests](#end-to-end-tests)
5. [Running Tests](#running-tests)
6. [Conclusion](#conclusion)

## Setup

Ensure you have the necessary dependencies installed:
```bash
npm install
```
Include a testing framework such as Jest and a testing utility like React Testing Library:
```bash
npm install --save-dev jest @testing-library/react @testing-library/jest-dom babel-jest @babel/preset-env @babel/preset-react
```
Configure Babel by creating a .babelrc file in the root of your project:
```bash
{
  "presets": ["@babel/preset-env", "@babel/preset-react"]
}

```
Configure Jest by creating a jest.config.js file in the root of your project:
```bash
module.exports = {
  testEnvironment: 'jsdom',
  transform: {
    '^.+\\.jsx?$': 'babel-jest',
  },
  setupFilesAfterEnv: ['<rootDir>/src/setupTests.js'],
};
```
Create a setupTests.js file in your src directory to configure Jest:
```bash
import '@testing-library/jest-dom/extend-expect';
```
Add a `test` script to `package.json`:
```bash
"scripts": {
  "dev": "vite",
  "build": "vite build",
  "serve": "vite preview",
  "test": "jest"
}
```
 

## Unit Tests

### Task Addition

#### Valid Input:

- Test that a task with valid input is added to the list.
- Check that the task is displayed in the UI.

#### Invalid Input:

- Test that an empty or invalid task input does not add a task.
- Verify that an error message or validation feedback is shown.

### Task Removal

#### Remove Task:

- Test that clicking the remove button deletes the task.
- Confirm the task is removed from the UI and data store.

### Completion Marking

#### Mark as Complete:

- Test that marking a task as complete updates the task status.
- Verify the UI reflects the task as completed (e.g., strikethrough text).

#### Toggle Completion:

- Test that toggling a completed task back to incomplete updates the status.
- Ensure the UI correctly updates to show the task as incomplete.

### Validation

#### Input Validation:

- Test that the input field enforces validation rules (e.g., non-empty).
- Verify appropriate validation messages are displayed.

## Integration Tests

### Dynamic Display

#### Task List Rendering:

- Test that tasks are dynamically displayed as they are added or removed.
- Ensure the UI updates in real-time without needing a page refresh.

### Sorting and Filtering

#### Sorting:

- Test that tasks are sorted correctly based on selected criteria (e.g., date, priority).
- Verify the sort order is correct in the UI.

#### Filtering:

- Test that tasks can be filtered by status (e.g., completed, pending).
- Confirm that only tasks matching the filter criteria are displayed.

## LocalStorage Integration

### Save to LocalStorage:

- Test that tasks are saved to localStorage when added, removed, or updated.
- Verify the localStorage data is correct.

### Load from LocalStorage:

- Test that tasks are loaded from localStorage on page load.
- Ensure the UI initializes with the correct task data.

## End-to-End Tests

### Full Workflow:

- Test the complete workflow of adding, marking as complete, filtering, sorting, and removing tasks.
- Verify the application behaves as expected through the entire process.

## Running Tests
Use the following command to run all tests:
```bash
npm test
```
For watching tests and running them interactively, use:
```bash
 npm test -- --watch
```

## Conclusion
This guide provides a structured approach to testing the To-Do List component. Following these tests will help ensure your application is robust and functions correctly under various scenarios.
