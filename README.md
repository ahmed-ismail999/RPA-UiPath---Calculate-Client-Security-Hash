# RPA UiPath--Calculate Client Security Hash

This RPA (Robotic Process Automation) project automates the process of working with **ACME System 1** to manage work items and perform client data processing. The project is divided into two main components: the **Dispatcher** and the **Performer**.

## Workflow Description

### 1. Launch and Login
The bot first launches **ACME System 1** and logs in using user credentials.

### 2. Work Item Navigation
After a successful login, the robot navigates to the **Work Items** section. It also opens **sha1.com**, a site used later for generating hash codes.

### 3. Dispatcher: Work Item Filtering and Queue Upload
In the **Dispatcher** phase, the bot:
- Retrieves all work items from **ACME System 1**.
- Filters the work items to retain only those of type **WI5**.
- Uploads the filtered work items to the **Orchestrator queue**.

### 4. Performer: Processing Work Items
In the **Performer** phase, the bot processes each work item:
- Extracts the **Client ID**, **Client Name**, and **Client Country** from each item.
- Uses these details to generate a **hash code** by interacting with **sha1.com**.

### 5. Hash Code Generation
The client details are used to generate a **hash code** from **sha1.com**, which is needed for further processing.

### 6. Updating Work Items
The bot then:
- Updates the corresponding work item in the **Orchestrator queue**.
- Marks the status of the work item as **Completed**.

### 7. End of Process
Once all the work items are processed and updated, the bot closes the session and completes the process.

---

### Technologies Used:
- **UiPath** for RPA automation.
- **Orchestrator** for queue management.
- **sha1.com** for hash code generation.
- **ACME System 1** for managing work items.

### How to Run the Project:
1. Open the project in **UiPath Studio**.
2. Set up the necessary credentials in the config file.
3. Run the **Dispatcher** process to filter and upload the work items.
4. Run the **Performer** process to process each work item and update the queue.
5. Monitor the queue in **Orchestrator** to view the status of the work items.
