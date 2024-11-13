# Task-Organizer
**Section 1 - Project Description**
1.1 Project Name:
    _Task Organizer_

1.2 Description:
    Overview - Task Organizer is a simple application designed to help users manage tasks by 
    allowing them to add, updates, delete and view tasks with deadlines. It categorizes tasks
    by status, suck as "Pending", "Completed" or "Overdue" to help users prioritize their
    workload effectively.

1.3 Revision History:
      Date                              Comment                               Author
    2024-10-30                     Initial draft created                Nishkarmanjit Kaur

**Section 2- Overview**
2.1 Purpose:
This document covers the high level requirements and system architecture for the Task Organizer module. The intended audience includes developers, project managers and testers involved in building and maintaining this application.

2.2 Scope:
The Task Organizer app will allow users to create, update, delete, and view tasks with 
deadlines. The application will be restricted to local storage (file/database on the local machine) for simplicity and will not include advanced features like reminders or task- sharing.

2.3 Requirements:
2.3.1 Functional Requirements
        The system shall allow users to add new tasks with a description and deadline. 
        The system shall allow users to mark tasks as "Completed" or "Pending."
        The system shall categorize tasks as "Pending," "Completed," or "Overdue."
        The system shall allow users to delete tasks that are no longer needed.
        The system shall provide the ability to sort tasks by deadline.

2.3.2 Non-Functional Requirements
         Performance: The system should respond within 2 seconds for all operations (add, 
                      update, delete, view).
         Reliability: The application should have 99% uptime when deployed and should be 
                      robust enough to handle typical user interactions without crashing.

2.3.3 Technical Requirements
         Hardware: Should run on any standard machine with at least 4GB RAM.
         Software: Developed in Java, using JavaFX or Swing for UI, and possibly SQLite or a 
                   simple file-based system for task storage.

2.3.4 Security Requirements
         Authentication: For simplicity, no user login will be required.
         Data Integrity: User task data will be saved locally and encrypted if possible to 
                         ensure privacy.

2.3.5 Estimates
      #	                 Description	                                      Hrs. Est.
1                        Requirements Gathering & Documentation	              4 hrs
2	                       UI Design & Prototyping	                            8 hrs
3	                       Database/Storage Integration	                        6 hrs
4	                       Core Functionality Development	                      12 hrs
5	                       Testing & Debugging	                                6 hrs
6	                       Documentation & Final Review	                        4 hrs
TOTAL:		                                                                    40 hrs

2.3.6 Traceability Matrix
     SRS Requirement	                    SDD Module
        Req 1	                            Section 2.3.1, Section 3.1 (Feature 1)
        Req 2          	                  Section 2.3.1, Section 3.1 (Feature 2)
        Req 3	                            Section 2.3.1, Section 3.1 (Feature 3)

**Section 3- System Architecture**
  3.1 Overview:
      The Task Organizer application has a client-server-like structure where the client-side 
      manages the UI, while server-side logic (running locally) processes the data. The 
      system’s primary components are the user interface, data processing logic, and local 
      data storage.

  3.2 Architectural Diagrams:  (Component Diagram)
       +------------------+
       |     UI (Client)  |
       +------------------+
             |
             v
 +------------------------+      +----------------------------+
 | Authentication Service |<--->|   Task Management Service  |
 +------------------------+      +----------------------------+
             |                             |
             v                             v
 +------------------------+      +----------------------------+
 |     Database           |<--->|   Backend Service          |
 +------------------------+      +----------------------------+
             |
             v
 +----------------------------+
 |   Notification Service     |
 +----------------------------+
             |
             v
      +----------------------+
      | Third-Party Services |
      +----------------------+


  **Section 4- Data Dictionary**
    Table	      Field	              Notes	                                  Type
    Task	      TaskID	            Unique Identifier	                      INT
                Title	              Description of the task	                VARCHAR
                Deadline	          Deadline for task completion	          DATE
                Status	            Task status (Pending/Completed)  	      VARCHAR

   ** Section 5- Data Design **  
   For Task Organizer application, the persistent/static data will involve a single main 
   entity: Task. The Task entity stores each individual task the user creates. Each task has 
   multiple attributes that describe it, such as a unique identifier, title, description, 
   deadline, and status. These attributes make it easier for the system to manage and display 
   tasks efficiently.
   _Attributes:_
   TaskID (Primary Key): A unique identifier for each task, ensuring each task record is 
                         distinct.
   Title: A brief, descriptive title of the task.
   Description: A more detailed description of the task, outlining what needs to be done.
   Deadline: The date and time by which the task should be completed.
   Status: The current state of the task, which can be either "Pending," "Completed," or 
           "Overdue."
   _Relationships:_
   In this simple model, Task is a standalone entity and does not have direct relationships 
   with other entities. However, if future updates introduce user accounts or categories, 
   relationships could be established where:
   User owns multiple Tasks (One-to-Many relationship).
   Category groups multiple Tasks based on type (e.g., "Work," "Personal"). 

              The Task Organizer application should provide a simple, intuitive interface allowing users to:

Add Tasks with a title, description, deadline, and status.
View Task List with details like task title, deadline, and status.
Edit or Delete Tasks as needed.
Filter and Sort Tasks based on status (Pending, Completed, Overdue).
Mark Tasks as Completed once finished.
                            ----------------------
                            |       Task          |
                            -----------------------
                            |  TaskID (PK) :INT   |
                            |  Title : VARCHAR    |
                            |  Description: TEXT  |
                            |  Deadline: DATETIME |
                            |  Status : VARCHAR   |
                            -----------------------

   **Section 6- User Interface Design**
   6.1 User Interface Design Interface Overview:
   The Task Organizer application should provide a simple, intuitive interface allowing users 
   to:
   Add Tasks with a title, description, deadline, and status.
   View Task List with details like task title, deadline, and status.
   Edit or Delete Tasks as needed.
   Filter and Sort Tasks based on status (Pending, Completed, Overdue).
   Mark Tasks as Completed once finished.
   6.2 User Interface Navigation Flow:
   Main Screen -> Add Task -> View Task -> Edit task -> Delete Task
   6.3 Use Cases/ User Function Description: 
   Use Case: Add Task
             Function- Allows users to add a new task with a description and deadline.
   Use Case: Edit Task
             Function- Allows users to modify existing tasks.
   Use Case: Delete Task
             Function- Allows users to remove tasks.

   
        
