# TODO-
1. The Building Blocks (struct and Array)
typedef struct { ... } Task;: This defines a custom data type called Task. Think of it as a template that groups three things together for every single task:

id: A unique number (1, 2, 3...) to find the task.

description: The text (e.g., "Study C Programming").

isCompleted: A simple switch (0 means "Not Done", 1 means "Done").

Task todoList[MAX_TASKS];: This creates a list (array) that can hold up to 100 of these Task structures. This is where your data lives.

2. The Main Loop (main)
The while(1) loop acts as the "engine" of the program. It keeps the program running endlessly so you can perform multiple actions (Add, then View, then Delete) without restarting the program.

It only stops when you type 5 (Exit), which runs return 0;.

3. Key Functions
addTask():

It asks you to type a task.

It uses fgets instead of scanf. This is important because scanf stops reading text when it hits a space. fgets allows you to type sentences like "Buy milk and eggs."

It saves the task into the next available slot in the todoList array.

viewTasks():

It loops through the array and prints every task.

It uses a fancy bit of logic (todoList[i].isCompleted ? 'X' : ' '). This is a "Ternary Operator." It says: If the task is completed, print an X; otherwise, print a space.

markCompleted():

It asks for an ID (e.g., 2).

It searches the array for that ID. If found, it changes isCompleted from 0 to 1.

deleteTask():

This is the most complex logic. When you delete a task (say, Task #2), you can't just leave a hole in the array.

The code shifts all the tasks that came after Task #2 to the left. Task #3 becomes the new Task #2, Task #4 becomes Task #3, and so on.

4. Special Helper: clearInputBuffer()
When you type a number (like 1 for the menu) and hit Enter, you actually send two things: the number 1 and a newline character (\n).

scanf takes the 1 but leaves the \n floating in the system.

The next time the program tries to read text (like your task description), it might accidentally read that old \n and think you finished typing before you even started.

clearInputBuffer() acts like a vacuum cleaner that eats up those leftover characters so your next input is clean.
