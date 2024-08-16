# Tasker-Project
Overview
Tasker is a Flask-based server that processes tasks asynchronously. Clients can submit tasks and receive a unique task ID (UUID) without waiting for immediate results.
The server processes these tasks in the background and stores the results in databases.

Supported Tasks:

Sum two numbers: Adds two integers and stores the result.
Multiply three numbers: Multiplies three integers and stores the result.
Fetch GitLab Group Info: Retrieves information about a specified GitLab group, including:
All projects in the group.
All users in the group.
Users per project.
The GitLab data is stored in a separate database.
Project Structure
server.py: The main Flask server handling task submissions.
tasks.py: Contains the task functions for sum, multiply, and GitLab group info retrieval.
database.py: Handles database operations for storing task results and GitLab information.
requirements.txt: List of Python dependencies.
Databases
tasks.db: Stores results for sum and multiply tasks.
gitlab_info.db: Stores GitLab group information.

**How to submit the tasker**

1.Start the Flask server:
  python server.py
  The server will be running on http://localhost:5000.
2.send a post request to the server:
  **Example Requests**
  Sum Two Numbers: curl -X POST http://localhost:5000/submit_task -H "Content-Type: application/json" -d '{"task_name": "sum", "params": {"a": 5, "b": 7}}'
  Multiply Three Numbers: curl -X POST http://localhost:5000/submit_task -H "Content-Type: application/json" -d '{"task_name": "multiply", "params": {"a": 2, "b": 3, "c": 4}}'
These requests will store the result in tasks.db.
