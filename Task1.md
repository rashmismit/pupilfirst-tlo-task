Prerequisites:
This tutorial assumes that you have a basic knowledge of JavaScript

Get started:
In this lesson, we will apply our knowledge of JavaScript Closures, to create a simple Todo manager.The implementation In this lesson, we will make use of the Node.js REPL. Open the terminal and run with the node command to go inside the REPL mode.

Add a todo:
The first thing we need to do is set up an array where we’ll place the todo list items.const todoList = () => all = [] Here, we will keep the list of all todos inside the all array.Each todo item will be an object with three properties:title, dueDate, completed (of type boolean)a boolean which helps us know if a task has been marked completed or not. 
For ex. { title: 'I need to go to gym', dueDate: '22-06-2022', completed: false } 
We will create a parent(in context of closure) todoList function. 
Now inside todoList, we need to define two child functions add and markAsComplete to perform respective operations. And in the end, we will make sure that the todoList function returns the list of all todos along with the add and markAsComplete function
let's define the add() function.

const todoList = () => { all = [] const add = (todoTask) => { all.push(todoTask) console.log(all) } The add() function takes a todoTask as argument, and pushes into the all array.

Similarly, we will define the markAsComplete() function.

const todoList = () => { all = [] const add = (todoTask) => { all.push(todoTask) console.log(all) } const markAsComplete = (index) => { all[index].completed = true console.log(all) } Here, the markAsComplete() function takes an argument called index. It updates the all array using the index, and marks that specific Todo as completed .

Finally, the task is pushed to the todoItems array, To complete the todoList function, we will return the all array and add, markAsComplete functions.

const todoList = () => { all = [] const add = (todoTask) => { all.push(todoTask) console.log(all) } const markAsComplete = (index) => { all[index].completed = true console.log(all) } return { all, add, markAsComplete }; } 

Execution:
Let's test it out First, in the terminal
 we will call the todoList() function.
todos.all [] // It will return an empty array

To add a new Todo:
todos.add({ title: 'I need to go to gym', dueDate: '22-06-2022', completed: false })
todos.add({ title: 'Have to buy potato', dueDate: '22-06-2022', completed: false }) 
Expected output:
todos.all [{ title: 'I need to go to gym', dueDate: '22-06-2022', completed: false }, { title: 'Have to buy potato', dueDate: '22-06-2022', completed: false }]

 To mark a Todo as complete:
todos.markAsComplete(1).Here 1 is the array index

Expected output:
[{ title: 'I need to go to gym', dueDate: '22-06-2022', completed: false }, { title: 'Have to buy potato', dueDate: '22-06-2022', completed: true }]
As we've learned before, in this example, the two functions add and markAsComplete had preserved the legacy variable all when the todoList() function was executed, and continued to preserve (closure) it.
