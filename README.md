# geo-tasks
Geo-based tasks tracker

Build an API to work with geo-based tasks. Use Elixir and PostgreSQL (recommended). All API endpoints should work with json body (not form-data). The result should be available as Github repo with commit history and the code covered by tests. Please commit the significant step to git, and we want to see how you evolved the source code.

Each request needs to be **authorized by token**. You can use pre-defined tokens stored on the backend side. Operate with tokens for two types of users:

1. Manager
1. Driver

Create tokens for more drivers and managers, not just 1-1.

Each task can be in 3 states:

1. New (Created task)
1. Assigned (The driver has picked this task)
1. Done (Task marked as completed by the driver)

### Access

* Manager can create tasks with two geo locations pickup and delivery
* Driver can get the list of tasks nearby (sorted by distance) by sending his current location 
* Driver can change the status of the task (to assigned/done). 
* Drivers can't create/delete tasks. 
* Managers can't change task status.

### Workflow:

1. The manager creates a task with location pickup [lat1, long1] and delivery [lat2,long2]
1. The driver gets the list of the nearest tasks by submitting current location [lat, long]
1. Driver picks one task from the list (the task becomes assigned)
1. Driver finishes the task (becomes done)
