# Amna-
إليك ملف README.md بتنسيق مناسب لمشروعك على GitHub. قم بنسخه ولصقه مباشرة في مستودعك:


---

# Pipe Execution Program

## Objective
This project demonstrates how to:
1. Use the `fork()` system call to create child processes.
2. Establish a pipe between two processes for inter-process communication (IPC).
3. Redirect data from one process to another using `dup()` and `dup2()` system calls.

---

## Group Information
- **Group Number**: [NAME]  
- **Index Numbers**: [List index numbers]  
- **Members**: [List group members]  

---

## Work Division
- **[Member 1]**: Implemented the creation of pipes and child processes.  
- **[Member 2]**: Handled error checking, input validation, and program testing.  
- **[Member 3]**: Created this README file and documented the design overview.  

---

## Design Overview
### Problem 1
1. **Child Process Creation**:  
   Create two child processes from the same parent process.

2. **Parent Process Behavior**:  
   - Waits for both child processes to terminate.  
   - Prints the exit status of each child upon termination.

### Problem 2
1. **Command Parsing**:  
   Separate commands based on the pipe (`|`) character.

2. **Pipe Creation**:  
   Use the `pipe()` system call to establish communication between processes.

3. **Child Processes Execution**:  
   - The first child executes the command before the pipe.  
   - The second child executes the command after the pipe and reads input from the first command.

4. **Parent Process Behavior**:  
   Waits for both child processes to finish execution.

5. **Error Handling**:  
   Handle invalid commands or unexpected inputs.

---

## Complete Specification
### Problem 1
1. Create two child processes from the same parent process.
2. Ensure the parent waits for both child processes to complete.
3. Print the exit status of each child upon termination.

### Problem 2
1. Execute commands passed as command-line arguments separated by a pipe (`|`).
2. The first child executes the first command and passes its output through the pipe.
3. The second child reads the input from the pipe and executes the second command.
4. The parent waits for both child processes to finish.

---

## Testing
### Functionality Testing
1. **Valid Commands**:  
   Example: `ls | grep .c`  
   Expected Output: Files matching the pattern `.c` are listed.

2. **Invalid Commands**:  
   Example: `invalid_cmd | grep`  
   Expected Output: Error message indicating an invalid command.

3. **Error Handling**:  
   Simulate pipe creation failure and verify proper error messages.

4. **Edge Cases**:  
   Empty input or no pipe character results in an error.

---

## Known Bugs or Limitations
1. The program does not handle multiple pipes (e.g., `ls | grep | wc`).
2. Partial handling of commands with excessive arguments or invalid syntax.

---

## Pre-requisites
1. Familiarity with system calls (`fork`, `wait`, `pipe`, `dup`, `dup2`, `execvp`).
2. Knowledge of inter-process communication (IPC).
3. Ability to read Unix manual pages.

---

## Test Cases
### Problem 1
1. **Two child processes successfully created**:  
   Input: Test program logic for child creation.  
   Output: Parent waits and prints exit statuses of both children.

### Problem 2
1. **Valid Command Execution**:  
   Input: `ls | wc`  
   Output: Correct word count.

2. **Invalid Command Handling**:  
   Input: `invalid_cmd | wc`  
   Output: Error message.

3. **Pipe Failure**:  
   Simulate pipe creation failure during execution.

---

## Submission Instructions
1. Create a directory named `p4-NAME`, where `NAME` is the group number.
2. Include the following files:
   - **Source Code**: All `.c` and `.h` files.
   - **Makefile**: For easy compilation.
   - **README File**: This file for documentation.
3. Compress the directory (excluding object files) and submit it.

---

## Compilation and Execution
To compile the program:
```bash
make

To run the program with commands:

./pipe_program "command1 | command2"

For example:

./pipe_program "ls | wc -l"

---

انسخ هذا الملف وأضفه كـ `README.md` في مستودعك على GitHub.
