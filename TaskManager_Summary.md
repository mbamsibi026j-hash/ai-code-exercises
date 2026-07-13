## Task Manager Codebase
## Project Structure
- Technologies/frameworks: Node.js (backend), React (frontend), MongoDB (database)
- Entry points: index.js (backend), src/index.js (frontend)
- Organization pattern: MVC with services and utilities
- Misconceptions corrected: Initially thought tasks were stored in flat files, but they're in a database schema

## Feature Exploration  Task Export to CSV
- Search keywords used: export, csv, download, file, serialize
- Relevant files/utilities found: utils/fileHelper.js, services/reportService.js
- Where export logic should live: TaskService + new route in TaskController
- Components affected: Task model, controller endpoint, UI button

## Domain Model Glossary
- Task = A unit of work assigned to a user
- TaskStatus = Lifecycle stage (open, in progress, completed, abandoned)
- TaskPriority = Urgency level (low, medium, high)
- User = Person who owns or is assigned tasks
- Abandoned = Tasks overdue > 7 days unless high priority

## Task Lifecycle Diagram (Text Sketch)
[User] ---> creates ---> [Task]
[Task] ---> has ---> [TaskStatus]
[Task] ---> has ---> [TaskPriority]
[Task] ---> may be exported ---> [CSV File]
[Task] ---> business rule ---> [Abandoned]

## Business Rule Application
- Rule: Tasks overdue > 7 days abandoned unless high priority
- Files to modify: Task entity, Task service, scheduled job
- Changes needed: Add abandoned status, write overdue check logic
- Team questions: Should abandoned tasks be visible? Notify users? Is "7 days" configurable?

## Final Reflection
Working through the prompts helped me move from guessing about the codebase to building a clear, structured understanding. At first, I only saw files and folders, but by applying the project structure, feature location, and domain model prompts, I connected technical components to real business rules. The domain model exercise was the most valuable because it forced me to think in business terms, not just code syntax. I now understand how tasks, statuses, priorities, and users interact, and how new rules like "abandoned tasks" fit into that flow. My next step is to deepen this understanding by tracing features end-to-end and reviewing test cases. Overall, this process gave me confidence in approaching unfamiliar codebases and a repeatable strategy I can use in future projects.
# Task Manager Project

This repository contains the Task Manager application and supporting documentation.
## Project Summary
For a detailed overview of the project structure, domain model, and feature exploration, see [Task Manager Codebase  Final Summary](TaskManager_Summary.md)
