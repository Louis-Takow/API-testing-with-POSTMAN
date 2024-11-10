# Project Name - Postman Collection Setup Guide for HEROKUAPP

This guide will walk you through the steps required to clone this repository, import the JSON file into Postman, and run the collection smoothly using **Postman Collection Runner** and **Newman** (CLI tool).

---

## Prerequisites

Before proceeding, make sure you have the following software installed on your computer:

- **Git**: Download and install from [Git's official website](https://git-scm.com/).
- **Postman**: Download and install from [Postman's official website](https://www.postman.com/).
- **Newman** (Optional, for CLI): Install it by running:
  ```bash
  npm install -g newman
  ```

---

## Steps to Clone and Import the JSON File into Postman

### Step 1: Clone the Repository

1. Open your terminal (Command Prompt, PowerShell, or Git Bash).
2. Run the following command to clone the repository:
   ```bash
   git clone <repository-url>
   ```
   > Replace `<repository-url>` with the actual URL of the GitHub repository. For example:
   ```bash
   git clone https://github.com/username/API-testing-with-POSTMAN.git
   ```

3. Once the repository is cloned, navigate to the project folder:
   ```bash
   cd repo-name
   ```

---

### Step 2: Open Postman

1. Launch the **Postman** application on your computer.

---

### Step 3: Import the JSON File into Postman

1. Click on the **“Import”** button located at the top-left corner of the Postman interface.
2. In the Import window, select the **“File”** tab.
3. Click on **“Upload Files”** and navigate to the project folder where the JSON files are located.
4. Select the JSON file and click **“Open”**.
5. Once imported, you should see the collection appear in the sidebar of your Postman interface. Repeat for enviroment and global variable JSON file.

---

### Step 4: Running the Collection

#### Option 1: Run with Postman Collection Runner

1. Expand the imported collection from the sidebar.
2. Click on the **“Run”** button (the button with the **play icon**) at the top-right of the collection interface.
3. The **Collection Runner** window will open, where you can select an environment (if applicable) and configure any other settings.
4. Once you’ve configured the environment and settings, click on the **“Run”** button to execute the collection.
5. Review the results of the requests in the **Collection Runner** output panel.

#### Option 2: Run with Newman (CLI Tool)

Newman is the command-line companion for Postman, and it allows you to run collections directly from the terminal.

1. Ensure you have **Newman** installed by running:
   ```bash
   newman -v
   ```
   If not installed, you can install it via npm:
   ```bash
   npm install -g newman
   ```

2. Use the following command to run the Postman collection with Newman:
   ```bash
   newman run "path_to_your_collection_file.postman_collection.json" -e "path_to_your_environment_file.postman_environment.json" -g "path_to_your_globals_file.postman_globals.json"
   ```
   > Replace `path_to_your_collection_file` with the location of your collection JSON file. Replace `path_to_your_environment_file` and `path_to_your_globals_file` with the locations of your environment and global variables JSON files, respectively.

---

## Test Scenarios

### Creating a Booking
- Sends a **POST** request to initiate a new booking.
- Confirms that the response status is **200**.
- Retrieves the `bookingid` from the response body and saves it to an environment variable.

### Reading a Booking
- Sends a **GET** request to fetch booking details using the stored booking ID.
- Confirms that the response status is **200**.

### Updating a Booking
- Sends a **PUT** request to modify the booking details using the stored booking ID.
- Confirms that the response status is **200**.

### Partially Updating a Booking
- Sends a **PATCH** request to partially modify the booking details using the stored booking ID.
- Confirms that the response status is **200**.
- Asserts the updated booking details.

### Deleting a Booking
- Sends a **DELETE** request to remove the booking using the stored booking ID.
- Confirms that the response status is **201**.

---

## Setting Up Environment Variables (If Applicable)

1. If the collection uses environment variables, go to the **Environments** tab in Postman.
2. Click on **“Add”** to create a new environment.
3. Define the required variables with appropriate values.
4. Select the created environment from the environment dropdown at the top-right of the interface.

---

## Best Practices

- **Validate Positive and Negative Path**: Test for valid, invalid, and unexpected conditions to ensure robustness.
- **Data Management**: Separate test data from your script by creating a base-URL global variable and using environment variables for reusable and sensitive data. This practice helps maintain security and improves the flexibility of your tests.

---

## Notes

- Make sure to replace any placeholder values in the requests (such as `{{baseUrl}}`, `{{apiKey}}`, etc.) with the actual values.
- Refer to the project's documentation for any API key setup, authentication requirements, or additional configuration needed:  
  https://restful-booker.herokuapp.com/apidoc/index.html

---

## Troubleshooting

- **Request Fails**: Ensure you have an active internet connection and the correct endpoint URLs.
- **Environment Variables Not Working**: Double-check the variable names and values in your environment settings.
- **Postman Version Compatibility**: Ensure that you are using an updated version of Postman to avoid any compatibility issues.
- **Newman Errors**: If running with Newman, make sure the file paths are correct and the required JSON files are accessible.

---

## Additional Resources

- [Postman Documentation](https://learning.postman.com/docs/getting-started/introduction/)
- [Git Documentation](https://git-scm.com/doc)
- [Newman Documentation](https://www.npmjs.com/package/newman)

---

## Author: Louis Takow
### LinkedIn: [Louis Takow](https://www.linkedin.com/in/louis-takow-istqb-certified-capm-8163b61b8/)
### Email: Louistt1995@gmail.com

Feel free to reach out if you encounter any issues or have questions. Happy testing!

--- 

This version now includes detailed test scenarios and best practices for your Postman collection.
