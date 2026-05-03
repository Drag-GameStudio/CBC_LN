
### 🚀 Powered by ADG System
The original version of this document offers a superior layout and faster navigation. 
**Check it out here:** [Full Documentation Interface](https://draggame-adg-frontend.hf.space/docs/adg_doc_ac382fdd4e28f34e0cf5bb1387925f20)
---

# Project Overview: Client-Server File Synchronization System

## **Project Title**
FileSync: A Client-Server File Synchronization System

---

## **Project Goal**
The FileSync project aims to provide a robust and user-friendly solution for synchronizing files between a client and server in a distributed environment. By leveraging a client-server architecture, RESTful APIs, and a web-based interface, this software addresses the challenge of maintaining consistent file states across multiple devices or systems. It ensures efficient file management, including adding, removing, modifying, and validating files and folders, while providing real-time synchronization and user-friendly controls.

---

## **Core Logic & Principles**
The FileSync system is built on a client-server architecture, where the client interacts with the server through RESTful APIs to perform file synchronization operations. The server, implemented using Flask, handles file and folder operations, manages metadata, and ensures data integrity. The client-side logic is responsible for initiating synchronization tasks, calculating file sizes, and tracking changes in local files.

Key components of the system include:
1. **Backend Logic**:
   - **Client (`connect.py`)**: Sends HTTP requests to the server for file and folder operations, such as adding, removing, modifying, and checking files.
   - **Server (`server.py`)**: Processes client requests via Flask routes and performs file system operations (e.g., saving, deleting, and updating files) while maintaining metadata using JSON files and timestamps.
   - **Synchronization (`synchronization.py`)**: Implements file existence and change detection using hashing algorithms and manages metadata for synchronization.

2. **Configuration Management**:
   - **Configuration (`config.py`)**: Stores global constants, such as server connection details, directory paths, and API endpoints.

3. **User Interface**:
   - **Web Interface (`visual.py` and `web/`)**: Provides a user-friendly interface for controlling synchronization processes. The UI is built with HTML, CSS, and JavaScript, and integrates with the backend using Eel for Python-JavaScript communication.

4. **Testing Framework**:
   - **Unit Tests (`tests/`)**: Validates the functionality of backend modules and interface workflows. Mocked HTTP requests and file operations ensure comprehensive test coverage without requiring real file dependencies.

5. **Functional Flow**:
   - The client initiates synchronization tasks by sending HTTP requests to the server, which processes these requests and updates the file system and metadata accordingly.
   - The web interface allows users to start the server, monitor synchronization progress, and manage files interactively.

---

## **Key Features**
- **File Synchronization**: Add, remove, modify, and validate files and folders between client and server.
- **Metadata Management**: Tracks file changes, timestamps, and synchronization status using JSON files.
- **Web-Based Interface**: Provides an intuitive UI for controlling synchronization processes and monitoring progress.
- **RESTful API Integration**: Enables seamless communication between client and server.
- **Real-Time File Change Detection**: Utilizes hashing algorithms to detect file modifications.
- **Automated Testing**: Includes unit tests for validating backend and interface functionalities.
- **Cross-Platform Compatibility**: Built using Python, Flask, and Eel, ensuring compatibility across various operating systems.

---

## **Dependencies**
To run the FileSync system, the following libraries and tools are required:
- **Python**: Core programming language for the project.
- **Flask**: Framework for building RESTful APIs and handling server-side logic.
- **Eel**: Library for integrating Python with JavaScript for the web-based UI.
- **Requests**: HTTP client for sending API requests from the client.
- **Hashlib**: Provides hashing algorithms for file change detection.
- **OS**: Facilitates file system operations.
- **Shutil**: Enables file and directory management.
- **JSON**: Handles metadata storage and retrieval.
- **Datetime**: Formats timestamps for metadata.
- **Unit Testing Frameworks**:
  - **MagicMock**: Mocks file uploads for testing.
  - **Flask Test Client**: Simulates HTTP requests during testing.

---

## **Conclusion**
FileSync is a comprehensive solution for managing file synchronization between a client and server. By combining a robust backend, a user-friendly web interface, and automated testing, this project ensures efficient and reliable file management in distributed systems. Its modular architecture and use of widely-adopted technologies make it scalable and adaptable to various use cases, from personal file synchronization to enterprise-level applications.
## Executive Navigation Tree

### 📂 Core Engine
- [Connect Class](#connect-class)
- [Connect Class Methods](#connect-class-methods)
- [Server Class](#server-class)
- [Server Initialization](#server-initialization)
- [Start Server](#start-server)
- [Server and Client](#server-and-client)
- [Client Class](#client-class)
- [API Endpoints](#api-endpoints)
- [Get Info](#get-info)

### ⚙️ Synchronization Module
- [DOP Module](#dop-module)
- [DOP Functions](#dop-functions)
- [Synchronization Checker](#synchronization-checker)
- [Synchronization Data](#synchronization-data)
- [Add File](#add-file)
- [Remove File](#remove-file)
- [Check Removed](#check-removed)
- [Add Folder](#add-folder)
- [Change File](#change-file)
- [Check File](#check-file)
- [Get Status](#get-status)
- [Start File](#start-file)
- [End File](#end-file)
- [Set Current File](#set-current-file)
- [Set Proces](#set-proces)

### 🧪 Testing Suite
- [Test Connect](#test-connect)
- [Test Add File](#test-add-file)
- [Test Remove File](#test-remove-file)
- [Test Change File](#test-change-file)
- [Test Add Folder](#test-add-folder)
- [Test Get Removed File](#test-get-removed-file)
- [Test Check File](#test-check-file)
- [Test Get Full Size](#test-get-full-size)
- [Test Syn](#test-syn)
- [Test Check Removed](#test-check-removed)
- [Flask API Endpoint Tests](#flask-api-endpoint-tests)

### 🎨 UI & Styling
- [Color Text](#color-text)
- [Change Text](#change-text)
- [UI Visual](#ui-visual)
- [UI Script JS](#ui-script-js)
- [Add Elements](#add-elements)
- [Elements](#elements)
- [Style CSS](#style-css)
- [Scrollbar](#scrollbar)
- [Body and Header](#body-and-header)
- [Chouse Mode](#chouse-mode)

### 📄 Configuration & Requirements
- [AutoDocConfig YML](#autodocconfig-yml)
- [Requirements TXT](#requirements-txt)
- [Test to Work](#test-to-work)
<a name="connect-class"></a>
## `Connect` Class: Client-Side File Synchronization Operations

The `Connect` class in `connect.py` is responsible for managing client-side file and folder operations. It communicates with the server via HTTP requests, using endpoints defined in the `comands_names` dictionary. This class is a critical component of the client-server file synchronization system, enabling the client to perform actions such as adding, removing, and checking files and folders on the server.

---
<a name="connect-class-methods"></a>
### Class Methods and Functional Breakdown

####
<a name="server-class"></a>
## Component: `Server` Class (Server Management)

**Purpose:**  
The `Server` class is responsible for managing the server instance, including retrieving server information and starting the server.

**Logic Flow:**  
1. **Initialization:**  
   - Initializes a `server.Server` object with the server's port (`config.PORT`).

2. **Retrieve Server Information (`Get_Info`):**  
   - Calls the `Get_Info` method of the `server.Server` object to retrieve the server's IP and port.

3. **Start Server (`Run`):**  
   - Calls the `Start_Server` method of the `server.Server` object to start the server.

**Data Contract:**
| Entity           | Type       | Role                  | Notes                                       |
|-------------------|------------|-----------------------|---------------------------------------------|
| `Server_Class`    | `Server`   | Internal Dependency   | Manages server operations.                 |
| `Get_Info`        | `method`   | Output                | Retrieves server IP and port information.  |
| `Run`             | `method`   | Action                | Starts the server.                         |


markdown
<a name="server-initialization"></a>
### Initialization: `__init__`

**Purpose:** Initializes the `Server` instance with the specified port and sets up the server directory.

**Logic Flow:**
1. Prints the server directory path from `config.SERVER_DIRECTORY`.
2. Initializes the server port with the provided value.

**Data Contract:**
| Entity       | Type   | Role                  | Notes                                |
|--------------|--------|-----------------------|--------------------------------------|
| `port`       | `int`  | Input                 | Port number for the server to use.   |
| `self.Port`  | `int`  | Internal State        | Stores the server's port number.     |

---
<a name="start-server"></a> `Start_Server`
Starts the server and updates the UI with the server link.

**Logic Flow**:
1. Retrieves the port and path values from the respective input fields.
2. Calls the `eel.Get_Info(port, path)` function to get the server link.
3. Updates the UI with the server link.
4. Starts the server using `eel.Start_Server()`.

**Inputs and Outputs**:
| Entity         | Type     | Role                           | Notes                                      |
|----------------|----------|--------------------------------|--------------------------------------------|
| `port_item`    | `HTMLInputElement` | Input field for server port. | Extracted from the DOM.                   |
| `path_item`    | `HTMLInputElement` | Input field for server path. | Extracted from the DOM.                   |
| `ip_text`      | `HTMLElement`      | Displays the server link.    | Updated with the server link.             |
| `port`         | `string`           | Server port.                 | Retrieved from `port_item.value`.         |
| `path`         | `string`           | Server path.                 | Retrieved from `path_item.value`.         |
| `response`     | `string`           | Server link (IP and port).   | Returned by `eel.Get_Info`.               |

---

#### <a name="syn"></a> `Syn`
Initiates the file synchronization process and updates the UI dynamically.

**Logic Flow**:
1. Retrieves the server IP and client path from input fields.
2. Updates the synchronization button text to indicate progress.
3. Calls `eel.Get_Full_Size(ip, path)` to calculate the total size of files to be synchronized.
4. Clears the UI logs for added, removed, and changed files.
5. Calls `eel.Synchronizate_Fun(size)` to perform synchronization and retrieve the results.

**Inputs and Outputs**:
| Entity         | Type     | Role                           | Notes                                      |
|----------------|----------|--------------------------------|--------------------------------------------|
| `ip_item`      | `HTMLInputElement` | Input field for server IP.    | Extracted from the DOM.                   |
| `path_item`    | `HTMLInputElement` | Input field for client path.  | Extracted from the DOM.                   |
| `ip`           | `string`           | Server IP address.            | Retrieved from `ip_item.value`.           |
| `path`         | `string`           | Client path.                  | Retrieved from `path_item.value`.         |
| `size`         | `float`            | Total file size to sync.      | Returned by `eel.Get_Full_Size`.          |
| `res`          | `object`           | Sync results.                 | Contains added, removed, and changed files.|

---

####
<a name="server-and-client"></a> Server and Client Sections
```css
.server, .client {
    margin-top: 30px;
    width: 100%;
}
.server .start_button button, .client .syn_button button {
    width: 300px;
    border: 0;
    height: 40px;
    border-radius: 40px;
    margin-left: 100px;
    font-size: 25px;
    font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
    background: rgba(201, 201, 201, 0.61);
}
```
- **Server Section:**
  - Contains a start button styled with rounded edges and a light gray background.
- **Client Section:**
  - Contains a synchronization button with similar styling to the server start button.

---

####
<a name="client-class"></a>
## Component: `Client` Class (Client-Side Synchronization)

**Purpose:**  
The `Client` class handles file synchronization between the client and server. It uses the `connect.Connect` class to interact with the server and manages local file operations.

**Logic Flow:**  
1. **Initialization:**  
   - Initializes a `connect.Connect` object with the server's IP and API endpoint mappings.
   - Initializes a `Data` dictionary to track added, removed, and changed files.
   - Initializes `Size` and `Current_Size` for tracking file sizes during synchronization.

2. **Calculate Total File Size (`Get_Full_Size`):**  
   - Recursively traverses the client directory (`config.CLIENT_DIRECTORY`) to calculate the total size of files that need to be synchronized.
   - For each file:
     - Checks if the file exists on the server using `Check_File`.
     - If the file does not exist, its size is added to the total size.

3. **Synchronize Files (`syn`):**  
   - Recursively traverses the client directory to synchronize files with the server.
   - For each file:
     - If the file is a folder, calls `Add_Folder` and recursively processes its contents.
     - If the file does not exist on the server, calls `Add_File` to upload it and updates the `Data` dictionary with the file's size.
     - If the file exists but has changed, calls `Change_File` to update it on the server and updates the `Data` dictionary with the file's size.
   - Identifies files that have been removed from the client using `Check_Removed` and deletes them from the server using `Remove_File`.

**Data Contract:**
| Entity           | Type       | Role                  | Notes                                       |
|-------------------|------------|-----------------------|---------------------------------------------|
| `current_path`    | `str`      | Input                 | Current directory path being synchronized.  |
| `element`         | `str`      | Intermediate Output   | Name of the file or folder being processed. |
| `res`             | `Response`| Intermediate Output   | Response from the server for file operations. |
| `size`            | `float`    | Intermediate Output   | Size of the file being processed (in GB).   |
| `proc`            | `float`    | Intermediate Output   | Synchronization progress percentage.        |
| `Data`            | `dict`     | Output                | Tracks added, removed, and changed files.   |

---
<a name="api-endpoints"></a>
## API Endpoints

The `Server` class defines multiple Flask routes to handle file and folder operations. Each route corresponds to a specific operation.

---
<a name="get-info"></a>
### Method: `Get_Info`

**Purpose:** Retrieves the server's hostname and IP address along with the port number.

**Logic Flow:**
1. Retrieves the hostname using `socket.gethostname()`.
2. Resolves the IP address using `socket.gethostbyname()`.
3. Returns a tuple containing the IP address and port.

**Data Contract:**
| Entity       | Type   | Role                  | Notes                                |
|--------------|--------|-----------------------|--------------------------------------|
| `hostname`   | `str`  | Internal State        | The server's hostname.               |
| `ip_address` | `str`  | Output                | The server's IP address.             |
| `self.Port`  | `int`  | Output                | The server's port number.            |

---
<a name="dop-module"></a>
## `dop.py`: Utility Functions for Logging and Text Formatting

The `dop.py` module provides utility functions for logging and text formatting. It includes functions to apply color formatting to text and placeholders for file operation logging.

---
<a name="dop-functions"></a>
### Functions and Functional Breakdown

####
<a name="synchronization-checker"></a>
## Component: `Checker` Class (File Change Detection)

**Purpose:**  
The `Checker` class is responsible for verifying the existence of files and detecting changes between a file on the server and a new version of the file provided by the client. It uses hashing to compare file contents.

**Logic Flow:**  
1. **File Existence Check (`File_Is_Be`):**  
   - Iterates through the directory specified by `self.Path`.
   - Compares each file name in the directory with the provided `file_name`.
   - Returns `True` if the file exists, otherwise `False`.

2. **File Change Detection (`Check_Changes`):**  
   - Opens the existing file in binary read mode.
   - Computes the MD5 hash of the existing file using the `Get_File_Hash` method.
   - Computes the MD5 hash of the new file provided by the client.
   - Compares the two hashes to determine if the files are different.
   - Returns `True` if the files are different, otherwise `False`.

3. **Hash Calculation (`Get_File_Hash`):**  
   - Reads the file in chunks of 4096 bytes.
   - Updates the MD5 hash with each chunk.
   - Returns the final hash as a hexadecimal string.

**Data Contract:**
| Entity       | Type   | Role                  | Notes                                                                 |
|--------------|--------|-----------------------|-----------------------------------------------------------------------|
| `file_name`  | `str`  | Input                 | Name of the file to check for existence or changes.                  |
| `new_file`   | `File` | Input                 | New file provided by the client for change detection.                |
| `file`       | `File` | Input                 | File object used for calculating MD5 hash.                           |
| `old_hash`   | `str`  | Intermediate Output   | MD5 hash of the existing file.                                       |
| `new_hash`   | `str`  | Intermediate Output   | MD5 hash of the new file.                                            |
| `response`   | `bool` | Output                | `True` if the file exists or has changes, `False` otherwise.         |

---
<a name="synchronization-data"></a>
## Component: `Data` Class (Metadata Management)

**Purpose:**  
The `Data` class handles reading, writing, and formatting metadata stored in a JSON file. It is used for managing server-side metadata related to file synchronization.

**Logic Flow:**  
1. **Write Metadata (`Write_Data`):**  
   - Reads the existing JSON file at `self.Data_Path`.
   - Updates the specified `key` with the provided `value`.
   - Writes the updated data back to the JSON file.  
   *(Note: This method is currently commented out in the provided code.)*

2. **Read Metadata (`Read_Data`):**  
   - Reads and parses the JSON file at `self.Data_Path`.
   - Returns the parsed data as a dictionary.  
   *(Note: This method is currently commented out in the provided code.)*

3. **Format Timestamp (`Get_Normal_Time`):**  
   - Converts a Unix timestamp (`time`) into a human-readable string in the format `YYYY-MM-DD HH:MM:SS`.
   - Returns the formatted timestamp.

**Data Contract:**
| Entity         | Type   | Role                  | Notes                                       |
|-----------------|--------|-----------------------|---------------------------------------------|
| `data_path`     | `str`  | Input                 | Path to the JSON file storing metadata.     |
| `key`           | `str`  | Input                 | Key to update in the JSON file.             |
| `value`         | `any`  | Input                 | Value to associate with the specified key.  |
| `time`          | `float`| Input                 | Unix timestamp to convert to a readable format. |
| `response`      | `dict` | Output                | Parsed JSON data or formatted timestamp.    |

---
<a name="add-file"></a>
### Endpoint: `/Add_File`

**Purpose:** Adds a file to the server.

**HTTP Method:** `POST`

**Logic Flow:**
1. Retrieves the file, its name, and the current path from the request.
2. Uses `synchronization.Checker` to verify if the file already exists.
3. If the file does not exist:
   - Saves the file to the specified directory.
   - Logs the operation using `dop.start_file` and `dop.end_file`.
   - Updates metadata using `synchronization.Data.Write_Data`.
4. Returns an appropriate HTTP response based on the operation's success.

**Data Contract:**
| Entity          | Type      | Role                  | Notes                                       |
|------------------|-----------|-----------------------|---------------------------------------------|
| `file`           | `File`    | Input                 | File to be uploaded.                        |
| `name`           | `str`     | Input                 | Name of the file.                           |
| `current_path`   | `str`     | Input                 | Path where the file will be saved.          |
| `response`       | `str`     | Output                | Status message indicating operation result. |

---
<a name="remove-file"></a>
### Endpoint: `/Remove_File`

**Purpose:** Removes a file or folder from the server.

**HTTP Method:** `POST`

**Logic Flow:**
1. Retrieves the file name and current path from the request.
2. Validates that the file or folder is not in the hidden `.info` directory.
3. Checks if the file or folder exists using `synchronization.Checker`.
4. If it exists:
   - Deletes the file or folder.
   - Returns the size of the deleted file or folder.
5. Returns an appropriate HTTP response if the file does not exist or is in the hidden directory.

**Data Contract:**
| Entity          | Type      | Role                  | Notes                                       |
|------------------|-----------|-----------------------|---------------------------------------------|
| `name`           | `str`     | Input                 | Name of the file or folder to be removed.   |
| `current_path`   | `str`     | Input                 | Path of the file or folder.                 |
| `response`       | `str`     | Output                | Status message or size of the deleted item. |

---
<a name="check-removed"></a>
### Endpoint: `/Check_Removed`

**Purpose:** Identifies files present on the server but missing on the client.

**HTTP Method:** `GET`

**Logic Flow:**
1. Retrieves the list of file names and current path from the request.
2. Compares the server's file list with the provided list.
3. Identifies and returns the names of files that are missing on the client.

**Data Contract:**
| Entity          | Type      | Role                  | Notes                                       |
|------------------|-----------|-----------------------|---------------------------------------------|
| `names`          | `list`    | Input                 | List of file names from the client.         |
| `current_path`   | `str`     | Input                 | Path of the directory to check.             |
| `response`       | `list`    | Output                | List of files missing on the client.        |

---
<a name="add-folder"></a>
### Endpoint: `/Add_Folder`

**Purpose:** Creates a new folder on the server.

**HTTP Method:** `POST`

**Logic Flow:**
1. Retrieves the folder name from the request.
2. Checks if the folder already exists.
3. If not, creates the folder.
4. Returns a success message.

**Data Contract:**
| Entity          | Type      | Role                  | Notes                                       |
|------------------|-----------|-----------------------|---------------------------------------------|
| `name`           | `str`     | Input                 | Name of the folder to be created.           |
| `response`       | `str`     | Output                | Status message indicating operation result. |

---
<a name="change-file"></a>
### Endpoint: `/Change_File`

**Purpose:** Updates an existing file on the server.

**HTTP Method:** `POST`

**Logic Flow:**
1. Retrieves the file, its name, and the current path from the request.
2. Uses `synchronization.Checker` to verify if the file exists.
3. If the file exists:
   - Replaces the existing file with the new one.
   - Logs the operation using `dop.start_file` and `dop.end_file`.
4. Returns an appropriate HTTP response based on the operation's success.

**Data Contract:**
| Entity          | Type      | Role                  | Notes                                       |
|------------------|-----------|-----------------------|---------------------------------------------|
| `file`           | `File`    | Input                 | File to replace the existing one.           |
| `name`           | `str`     | Input                 | Name of the file.                           |
| `current_path`   | `str`     | Input                 | Path of the file to be replaced.            |
| `response`       | `str`     | Output                | Status message indicating operation result. |

---
<a name="check-file"></a>
### Endpoint: `/Check_File`

**Purpose:** Checks if a file exists and optionally verifies its content.

**HTTP Method:** `GET`

**Logic Flow:**
1. Retrieves the file, its name, current path, and type of check from the request.
2. Uses `synchronization.Checker` to verify if the file exists.
3. If the file exists:
   - If `type_check` is `1`, compares the file's content with the provided file.
   - Returns the result of the check.
4. Returns an appropriate HTTP response if the file does not exist or an error occurs.

**Data Contract:**
| Entity          | Type      | Role                  | Notes                                       |
|------------------|-----------|-----------------------|---------------------------------------------|
| `file`           | `File`    | Input                 | File to be checked.                         |
| `name`           | `str`     | Input                 | Name of the file.                           |
| `current_path`   | `str`     | Input                 | Path of the file to be checked.             |
| `type_check`     | `int`     | Input                 | Type of check (0: existence, 1: content).   |
| `response`       | `str`     | Output                | Result of the check.                        |

---
<a name="get-status"></a>
### Endpoint: `/Get_Status`

**Purpose:** Retrieves the current server metadata.

**HTTP Method:** `GET`

**Logic Flow:**
1. Uses `synchronization.Data.Read_Data` to read the server's metadata.
2. Returns the metadata as a response.

**Data Contract:**
| Entity          | Type      | Role                  | Notes                                       |
|------------------|-----------|-----------------------|---------------------------------------------|
| `response`       | `dict`    | Output                | Server metadata as a JSON object.          |


markdown
<a name="start-file"></a> `start_file(name: str)`
**Purpose:** Placeholder function for logging the start of file processing.

**Logic Flow:**
- Currently, this function is not implemented. It is intended to log the start of file processing.

**Data Contract:**
| Entity   | Type      | Role                  | Notes                                       |
|----------|-----------|-----------------------|---------------------------------------------|
| `name`   | `str`     | Input                 | Name of the file being processed.           |

---

####
<a name="end-file"></a> `end_file(name: str)`
**Purpose:** Placeholder function for logging the end of file processing.

**Logic Flow:**
- Currently, this function is not implemented. It is intended to log the end of file processing.

**Data Contract:**
| Entity   | Type      | Role                  | Notes                                       |
|----------|-----------|-----------------------|---------------------------------------------|
| `name`   | `str`     | Input                 | Name of the file being processed.           |

---

####
<a name="set-current-file"></a> `Set_Current_File`
Updates the UI with the name of the current file being processed.

**Logic Flow**:
1. Retrieves the UI element for displaying the current file name.
2. Updates the element's text content with the provided `file_name`.

**Inputs and Outputs**:
| Entity         | Type     | Role                           | Notes                                      |
|----------------|----------|--------------------------------|--------------------------------------------|
| `file_name`    | `string`           | Name of the current file.     | Passed as a parameter to the function.    |
| `text`         | `HTMLElement`      | UI element for file name.     | Extracted from the DOM.                   |

---

####
<a name="set-proces"></a> `Set_Proces`
Updates the synchronization progress in the UI.

**Logic Flow**:
1. Retrieves the synchronization button element from the DOM.
2. Updates the button text with the current progress percentage.
3. If progress reaches 99%, updates the button text to indicate completion.

**Inputs and Outputs**:
| Entity         | Type     | Role                           | Notes                                      |
|----------------|----------|--------------------------------|--------------------------------------------|
| `proc`         | `float`            | Synchronization progress.    | Passed as a parameter to the function.    |
| `button_syn`   | `HTMLElement`      | Synchronization button element. | Extracted from the DOM.                   |

---

### Interactions with Other Components

1. **Backend (`visual.py`):**
   - The `eel` functions exposed in `visual.py` are called to perform server and client operations:
     - `Get_Info`
     - `Start_Server`
     - `Get_Full_Size`
     - `Synchronizate_Fun`
     - `Set_Current_File`
     - `Set_Proces`
     - `Add_elements`

2. **Frontend (`index.html`):**
   - The DOM elements are dynamically updated to reflect the current state of server and client operations.
   - Elements such as buttons, input fields, and logs are manipulated using JavaScript.

---

### Key Notes
> - Ensure the `eel` library is properly initialized and configured in the Python backend to enable seamless communication between Python and JavaScript.
> - The `Add_elements` function assumes that the input array `el` contains two elements: the file name and its size in bytes.
> - The `Set_Proces` function is designed to handle progress updates up to 99%. Additional handling may be required for edge cases.


markdown
<a name="test-connect"></a>
## Unit Tests for `connect.py`

This file contains unit tests for the `Connect` class, which is responsible for client-side operations such as file and folder management via HTTP requests. The tests utilize the `pytest` framework and `unittest.mock` for mocking external dependencies like HTTP requests.

---
<a name="test-add-file"></a>
### **Test: Add File Endpoint**

#### **Purpose**
Validates the `/Add_File` endpoint for uploading files to the server.

#### **Test Logic**
1. A Flask `test_client` is initialized in testing mode.
2. A mock file (`MagicMock`) is created to simulate a file upload.
3. A POST request is sent to `/Add_File` with:
   - Form data: `name` (file name) and `current path` (file directory).
   - File data: Mock file object.
4. The test asserts that the response status code is either `200` or `201`.

#### **Data Contract**
| Entity       | Type       | Role                       | Notes                                      |
|--------------|------------|----------------------------|--------------------------------------------|
| `client`     | `FlaskClient` | Simulates HTTP requests   | Used to send requests to the Flask app.    |
| `file_data`  | `dict`     | Mock file upload           | Contains a `MagicMock` object for the file.|
| `form_data`  | `dict`     | Metadata for the file      | Includes `name` and `current path`.        |
| `response`   | `Response` | Response from the endpoint | Contains `status_code` for validation.     |

---
<a name="test-remove-file"></a>
### Test: `test_remove_file`

This test verifies the `Remove_File` method, which sends a request to delete a file on the server.

#### **Logic Flow**
1. A mock for `requests.post` is created.
2. A mock response is configured with a status code of `200` and a response text of `"File removed"`.
3. A `Connect` object is instantiated with the server IP and command mappings.
4. The `Remove_File` method is called with the file name and its path.
5. The test verifies that `requests.post` is called with the correct URL and data.
6. The response status code is asserted to be `200`.

#### **Data Contract**
| Entity         | Type     | Role                          | Notes                                      |
|----------------|----------|-------------------------------|--------------------------------------------|
| `ip`           | `str`    | Server base URL               | Example: `http://localhost`.              |
| `commands`     | `dict`   | Command-to-endpoint mapping   | Example: `{'Remove File': 'Remove_File'}`.|
| `file_path`    | `str`    | Name of the file to be removed| Example: `test.txt`.                       |
| `current_path` | `str`    | Path to the file              | Example: `C:\\Users\\...\\Client\\`.       |
| `response`     | `object` | Response from the server      | Contains `status_code` and `text`.         |

---
<a name="test-change-file"></a>
### **Test: Change File Endpoint**

#### **Purpose**
Validates the `/Change_File` endpoint for modifying existing files on the server.

#### **Test Logic**
1. A Flask `test_client` is initialized in testing mode.
2. A mock file (`MagicMock`) is created to simulate a file upload.
3. A POST request is sent to `/Change_File` with:
   - Form data: `name` (file name) and `current path` (file directory).
   - File data: Mock file object.
4. The test asserts that the response status code is either `200` or `201`.

#### **Data Contract**
| Entity       | Type       | Role                       | Notes                                      |
|--------------|------------|----------------------------|--------------------------------------------|
| `client`     | `FlaskClient` | Simulates HTTP requests   | Used to send requests to the Flask app.    |
| `file_data`  | `dict`     | Mock file upload           | Contains a `MagicMock` object for the file.|
| `form_data`  | `dict`     | Metadata for the file      | Includes `name` and `current path`.        |
| `response`   | `Response` | Response from the endpoint | Contains `status_code` for validation.     |

---
<a name="test-add-folder"></a>
### Test: `test_add_folder`

This test validates the `Add_Folder` method, which sends a request to create a folder on the server.

#### **Logic Flow**
1. A mock for `requests.post` is created.
2. A mock response is configured with a status code of `200` and a response text of `"True"`.
3. A `Connect` object is instantiated with the server IP and command mappings.
4. The `Add_Folder` method is called with the folder path.
5. The test verifies that `requests.post` is called with the correct URL and data.
6. The response status code is asserted to be `200`.

#### **Data Contract**
| Entity         | Type     | Role                          | Notes                                      |
|----------------|----------|-------------------------------|--------------------------------------------|
| `ip`           | `str`    | Server base URL               | Example: `http://localhost`.              |
| `commands`     | `dict`   | Command-to-endpoint mapping   | Example: `{'Add Folder': 'Add_Folder'}`.  |
| `file_path`    | `str`    | Path of the folder to add     | Example: `test_path`.                      |
| `response`     | `object` | Response from the server      | Contains `status_code` and `text`.         |

---
<a name="test-get-removed-file"></a>
### Test: `test_get_removed_file`

This test ensures the `Check_Removed` method correctly identifies removed files by sending a request to the server.

#### **Logic Flow**
1. A mock for `requests.get` is created.
2. A mock response is configured with a status code of `200` and a response text containing a list of removed files.
3. A `Connect` object is instantiated with the server IP and command mappings.
4. The `Check_Removed` method is called with a list of file names and the current path.
5. The test verifies that `requests.get` is called with the correct URL and data.
6. The response is asserted to match the expected list of removed files.

#### **Data Contract**
| Entity         | Type     | Role                          | Notes                                      |
|----------------|----------|-------------------------------|--------------------------------------------|
| `ip`           | `str`    | Server base URL               | Example: `http://localhost`.              |
| `commands`     | `dict`   | Command-to-endpoint mapping   | Example: `{'Check Removed': 'Check_Removed'}`.|
| `file_names`   | `list`   | List of file names to check   | Example: `['test_path', 'second.txt']`.    |
| `current_path` | `str`    | Path to the files             | Example: `\\Client`.                       |
| `response`     | `list`   | List of removed files         | Example: `["test.txt"]`.                   |

---
<a name="test-check-file"></a>
### **Test: Check File Endpoint**

#### **Purpose**
Validates the `/Check_File` endpoint for checking file existence and content integrity on the server.

#### **Test Logic**
1. A Flask `test_client` is initialized in testing mode.
2. Two test cases are executed:
   - **Case 1:** File existence check.
     - A GET request is sent to `/Check_File` with:
       - Form data: `name` (file name), `current path` (file directory), and `type check` (set to `0` for existence check).
       - File data: Mock file object.
     - The test asserts that the response status code is either `200` or `201`.
   - **Case 2:** File content integrity check.
     - A GET request is sent to `/Check_File` with:
       - Form data: `name` (file name), `current path` (file directory), and `type check` (set to `1` for content check).
       - File data: Actual file object opened in binary mode.
     - The test asserts that the response status code is either `200` or `201`.

#### **Data Contract**
| Entity       | Type       | Role                       | Notes                                      |
|--------------|------------|----------------------------|--------------------------------------------|
| `client`     | `FlaskClient` | Simulates HTTP requests   | Used to send requests to the Flask app.    |
| `form_data`  | `dict`     | Metadata for file checks   | Includes `name`, `current path`, and `type check`. |
| `from_file`  | `dict`     | File data for upload       | Contains a `MagicMock` or actual file object. |
| `response`   | `Response` | Response from the endpoint | Contains `status_code` for validation.     |

---

### **Key Notes**
> - The tests utilize `unittest` and `unittest.mock.MagicMock` to simulate file uploads and server interactions.
> - The `test_client` provided by Flask is used to simulate HTTP requests to the API endpoints.
> - Each test ensures that the respective endpoint responds with a valid status code (`200` or `201`) and handles the provided input correctly.
> - The test suite is designed to validate the core functionality of the backend API endpoints without requiring actual file system operations.
<a name="test-get-full-size"></a>
## Test: `test_get_full_size`

This test validates the `Get_Full_Size` method of the `Client` class, which calculates the total size of files in a given directory.

### **Logic Flow**
1. A mock for the `Check_File` method in the `Backend.connect.Connect` class is created using the `patch_check_file` fixture.
2. A mock response is configured with the `text` attribute set to `"False"`.
3. The `Client` class is instantiated with two mock functions passed as arguments.
4. The `Get_Full_Size` method is called with a specified `current_path`.
5. The test verifies that `Check_File` is called once with the expected parameters.
6. The return value of `Get_Full_Size` is asserted to be greater than or equal to `0`.

### **Data Contract**
| Entity           | Type       | Role                            | Notes                                      |
|------------------|------------|---------------------------------|--------------------------------------------|
| `patch_check_file` | `fixture` | Mock for `Check_File` method    | Simulates server response for file checks. |
| `mock_response`  | `object`   | Mock response object            | Contains `text` attribute set to `"False"`.|
| `current_path`   | `str`      | Directory path to calculate size| Example: `C:\\Users\\...\\Client\\`.       |
| `size`           | `int`      | Total size of files in directory| Must be `>= 0`.                            |

---
<a name="test-syn"></a>
## Test: `test_syn`

This test validates the `syn` method of the `Client` class, which synchronizes local files with the server by performing various file operations such as checking, adding, changing, removing, and adding folders.

### **Logic Flow**
1. Mocks are created for the following methods in the `Backend.connect.Connect` class:
   - `Check_File`
   - `Add_File`
   - `Change_File`
   - `Check_Removed`
   - `Remove_File`
   - `Add_Folder`
2. Mock responses are configured for each method:
   - `Check_File`: Returns a `MagicMock` object with `text` set to `"True"`.
   - `Add_File`: Returns a tuple with a `MagicMock` object (status code `200`) and a file size of `100`.
   - `Change_File`: Returns a `MagicMock` object with status code `200`.
   - `Check_Removed`: Returns a list of removed files: `["test.txt", "test1.txt"]`.
   - `Remove_File`: Returns a `MagicMock` object with status code `200` and `text` set to `"100"`.
   - `Add_Folder`: Returns a `MagicMock` object with status code `200` and `text` set to `"Ok"`.
3. The `Client` class is instantiated with two mock functions passed as arguments.
4. The `Size` and `Current_Size` attributes of the `Client` instance are set to `500`.
5. The `syn` method is called with a specified `current_path`.
6. The test verifies that all mocked methods are called with the correct parameters.

### **Data Contract**
| Entity              | Type       | Role                              | Notes                                      |
|---------------------|------------|-----------------------------------|--------------------------------------------|
| `patch_check_file`  | `fixture`  | Mock for `Check_File` method      | Simulates server response for file checks. |
| `patch_add_file`    | `fixture`  | Mock for `Add_File` method        | Simulates server response for file addition.|
| `patch_change_file` | `fixture`  | Mock for `Change_File` method     | Simulates server response for file changes.|
| `patch_check_removed` | `fixture`| Mock for `Check_Removed` method   | Simulates server response for removed files.|
| `patch_remove_file` | `fixture`  | Mock for `Remove_File` method     | Simulates server response for file removal.|
| `patch_add_folder`  | `fixture`  | Mock for `Add_Folder` method      | Simulates server response for folder addition.|
| `mock_response`     | `object`   | Mock response object              | Contains attributes like `text` and `status_code`.|
| `current_path`      | `str`      | Directory path for synchronization| Example: `C:\\Users\\...\\Client\\`.       |
| `client.Size`       | `int`      | Total size of files               | Example: `500`.                            |
| `client.Current_Size` | `int`    | Current size of files             | Example: `500`.                            |

---

### Key Notes
> - The tests utilize `pytest` fixtures to mock external dependencies, ensuring isolation from the actual server and file system.
> - The `mock_open_fixture` creates a mock file for testing purposes, ensuring that the `Client` class interacts with a simulated file system.
> - The `test_syn` method covers a comprehensive range of file synchronization operations, ensuring the correctness of the `syn` method under various scenarios.
> - Mock responses are configured to simulate different server responses, allowing for robust testing of the `Client` class methods.


markdown
<a name="test-check-removed"></a>
### **Test: Check Removed Endpoint**

#### **Purpose**
Validates the `/Check_Removed` endpoint for identifying files that have been removed from the server.

#### **Test Logic**
1. A Flask `test_client` is initialized in testing mode.
2. A GET request is sent to `/Check_Removed` with:
   - Form data: `names` (list of file names) and `current_path` (directory path).
3. The test asserts that the response status code is either `200` or `201`.

#### **Data Contract**
| Entity       | Type       | Role                       | Notes                                      |
|--------------|------------|----------------------------|--------------------------------------------|
| `client`     | `FlaskClient` | Simulates HTTP requests   | Used to send requests to the Flask app.    |
| `form_data`  | `dict`     | Metadata for removed files | Includes `names` and `current_path`.       |
| `response`   | `Response` | Response from the endpoint | Contains `status_code` for validation.     |

---
<a name="flask-api-endpoint-tests"></a>
## Flask API Endpoint Tests for `server.py`

This test suite validates the functionality of the REST API endpoints defined in the `server.py` module of the backend. The tests simulate client requests using Flask's `test_client` and mock file uploads to ensure proper API behavior without requiring actual file system interactions.

---
<a name="color-text"></a> `Color_Text(color: Enum, text: str) -> str`
**Purpose:** Applies color formatting to a given text string.

**Logic Flow:**
1. Uses the `colorama` library to apply the specified color to the input text.
2. Resets the style after applying the color.

**Data Contract:**
| Entity   | Type      | Role                  | Notes                                       |
|----------|-----------|-----------------------|---------------------------------------------|
| `color`  | `Enum`    | Input                 | Color code from the `colorama` library.     |
| `text`   | `str`     | Input                 | The text to be formatted.                   |
| `result` | `str`     | Output                | Color-formatted text.                       |

---

####
<a name="change-text"></a> `Change_Text`
Updates the synchronization button text with a loading animation.

**Logic Flow**:
1. Updates the button text with the provided `text` parameter.
2. Adds a loading animation by appending dots to the text at regular intervals.
3. Resets the animation after three dots.

**Inputs and Outputs**:
| Entity         | Type     | Role                           | Notes                                      |
|----------------|----------|--------------------------------|--------------------------------------------|
| `text`         | `string`           | Text to display on the button. | Passed as a parameter to the function.    |
| `button_syn`   | `HTMLElement`      | Synchronization button element. | Extracted from the DOM.                   |
| `timer`        | `number`           | Timer ID for the animation.    | Used to manage the animation loop.        |

---

####
<a name="ui-visual"></a>
## Component: `visual.py` (Web Interface Integration)

**Purpose:**  
The `visual.py` module serves as the bridge between the Python backend and the web-based user interface, enabling user interaction for server management and file synchronization. It uses the `eel` library to expose Python functions to JavaScript, allowing seamless communication between the backend and the frontend.

---

### Functional Logic

1. **Initialization:**
   - The `eel.init("UI/web")` function sets the directory containing the HTML, CSS, and JavaScript files for the web interface.
   - The `eel.start("index.html", port=808, size=(500, 500))` function launches the web application on port 808 with a window size of 500x500 pixels.

2. **Path Refactoring (`Refactor_Path`):**
   - Converts Windows-style file paths by replacing single backslashes (`\`) with double backslashes (`\\`) and appending a trailing double backslash.
   - **Input:** A string representing a file path.
   - **Output:** A reformatted string with double backslashes.

3. **Server Management:**
   - **`Start_Server`:** Initializes a `Server` object from `main.py` and starts the server by calling its `Run` method.
   - **`Get_Info`:** Updates the server port and directory path in the `config` module, retrieves the server's IP and port using the `Get_Info` method of the `Server` object, and constructs the server link (e.g., `http://<ip>:<port>`).

4. **Progress and UI Updates:**
   - **`Set_Proc`:** Updates the synchronization progress in the UI by calling the exposed JavaScript function `Set_Proces`.
   - **`Add_Block`:** Adds a new file or folder to the UI log under the "Add elements" section by calling the exposed JavaScript function `Add_elements`.
   - **`Set_Current_File`:** Updates the UI to display the current file being processed by calling the exposed JavaScript function `Set_Current_File`.

5. **Delegation Helpers:**
   - **`Delegate_Proces`:** Delegates progress updates to the `Set_Proc` function.
   - **`Delegate_Add_Block`:** Delegates the addition of a file or folder to the UI log and updates the current file being processed.

6. **Client Operations:**
   - **`Get_Full_Size`:** 
     - Updates the client IP and directory path in the `config` module.
     - Initializes a `Client` object from `main.py` with the progress and UI update functions as callbacks.
     - Calls the `Get_Full_Size` method of the `Client` object to calculate the total size of files to be synchronized.
   - **`Synchronizate_Fun`:**
     - Initializes a `Client` object from `main.py` with the progress and UI update functions as callbacks.
     - Sets the current and total size of files to be synchronized.
     - Calls the `syn` method of the `Client` object to perform the synchronization process.
     - Returns the `Data` dictionary containing information about added, removed, and changed files.

---

### Data Contract

#### Python Functions Exposed to JavaScript
| Function Name       | Input Parameters                          | Output Type | Role                                                                 |
|---------------------|-------------------------------------------|-------------|----------------------------------------------------------------------|
| `Start_Server`      | None                                      | None        | Starts the server.                                                   |
| `Get_Info`          | `port: int`, `path: str`                  | `str`       | Returns the server link (IP and port).                               |
| `Set_Proc`          | `proc: float`                             | None        | Updates synchronization progress in the UI.                          |
| `Add_Block`         | `element: str`, `wei: int`                | None        | Adds a file or folder to the "Add elements" log in the UI.           |
| `Set_Current_File`  | `element: str`                            | None        | Updates the UI with the current file being processed.                |
| `Get_Full_Size`     | `link: str`, `path: str`                  | `float`     | Calculates and returns the total size of files to be synchronized.   |
| `Synchronizate_Fun` | `Size: float`                             | `dict`      | Synchronizes files and returns a dictionary of added/removed files.  |

#### Internal Functions
| Function Name       | Input Parameters                          | Output Type | Role                                                                 |
|---------------------|-------------------------------------------|-------------|----------------------------------------------------------------------|
| `Refactor_Path`     | `path: str`                               | `str`       | Refactors file paths for compatibility with Windows systems.         |
| `Delegate_Proces`   | `Proc: int`                               | None        | Delegates progress updates to the `Set_Proc` function.               |
| `Delegate_Add_Block`| `element: str`, `wei: int`                | None        | Delegates file addition to the UI log and updates the current file.  |

---

### Interactions with Other Components

1. **Backend (`main.py`):**
   - The `visual.py` module interacts with the `Server` and `Client` classes in `main.py` to manage server operations and perform file synchronization.

2. **Frontend (`index.html`):**
   - The web interface is defined in `index.html`, with JavaScript functions exposed via `eel.js` for seamless communication with the backend.
   - Functions such as `Set_Proces`, `Add_elements`, and `Set_Current_File` are called to update the UI dynamically during synchronization.

3. **Configuration (`config.py`):**
   - The `config` module is used to store and update global configuration parameters, such as the server port, server directory, client directory, and server IP.

---

### Key Notes
> - The `visual.py` module relies heavily on the `eel` library for Python-JavaScript communication. Ensure `eel.js` is included in the frontend for proper functionality.
> - The `Refactor_Path` function is specific to Windows file paths. Cross-platform compatibility may require additional handling.
> - The `Synchronizate_Fun` function assumes that the `Client` class in `main.py` is correctly implemented and that the `syn` method updates the `Data` dictionary with synchronization results.


markdown
<a name="ui-script-js"></a>
## JavaScript Module: `script.js` - UI Logic for Server and Client Operations

This JavaScript file defines the client-side logic for interacting with the web-based user interface. It facilitates communication with the Python backend using the `eel` library and manages various UI elements during server and client operations.

---

### Functional Responsibility
This module provides the following key functionalities:
- **Server Management**: Starting the server and displaying the server link.
- **File Synchronization**: Initiating and managing the file synchronization process between the client and server.
- **UI Updates**: Dynamically updating the user interface, including progress indicators, file logs, and current file status.

---

### Key Functions

####
<a name="add-elements"></a> `Add_elements`
Dynamically adds file elements to the UI log.

**Logic Flow**:
1. Stops any ongoing timer.
2. Retrieves the parent element for the log from the DOM.
3. Creates a new `div` element for the file, including its name and size.
4. Appends the new element to the parent log.

**Inputs and Outputs**:
| Entity         | Type     | Role                           | Notes                                      |
|----------------|----------|--------------------------------|--------------------------------------------|
| `el`           | `array`            | File details (name, size).   | Passed as a parameter to the function.    |
| `path`         | `string`           | Selector for the log element.| Passed as a parameter to the function.    |
| `parrent`      | `HTMLElement`      | Parent log element.           | Extracted from the DOM.                   |
| `newDiv`       | `HTMLElement`      | New file element.             | Created dynamically and appended to `parrent`. |

---

####
<a name="elements"></a> Elements Section
```css
.elements .contain {
    width: 100%;
    background: rgb(200, 232, 247);
    color: rgb(97, 97, 97);
    height: 70px;
    margin-left: 0;
}
.elements .contain h1 {
    font-family: Arial, Helvetica, sans-serif;
    font-weight: 200;
    margin-left: 30px;
    display: inline-block;
    width: 220px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}
.elements .contain .wei {
    font-family: Arial, Helvetica, sans-serif;
    font-weight: 200;
    position: absolute;
    margin-top: 20px;
    left: 250px;
}
```
- **Purpose:** Styles individual file elements in the UI log, including file name and size. Implements ellipsis for long file names.

---

### Key Notes
> - The CSS file ensures a responsive and modern design for the web-based interface.
> - The `::-webkit-scrollbar` rule hides the scrollbar for a cleaner appearance.
> - The `elements .contain h1` rule ensures that long file names are truncated with ellipses to maintain a neat layout.
> - The `Chouse_Mode` buttons include a hover effect for better user interaction feedback.

---
<a name="style-css"></a>
## `style.css` - Styling for Web Interface

This file defines the CSS styling for the web-based user interface of the file synchronization system. It ensures a clean and responsive design, providing a user-friendly experience for interacting with the client-server application.

---

### Key Styling Components

####
<a name="scrollbar"></a> Custom Scrollbar
```css
::-webkit-scrollbar {
    width: 0px; /* For vertical scrollbar */
    height: 0; /* For horizontal scrollbar */
}
```
- **Purpose:** Hides the scrollbar for a cleaner UI appearance.

---

####
<a name="body-and-header"></a> Body and Header
```css
body {
    margin: 0;
    padding: 0;
}
.header {
    background: black;
    position: absolute;
    top: 0;
    width: 100%;
    margin: 0;
    height: 100px;
}
.header h1 {
    color: white;
    text-align: center;
    margin-top: 20px;
    font-size: 29px;
    font-weight: 200;
    font-family: Arial, Helvetica, sans-serif;
}
```
- **Body:** Removes default margin and padding for a clean layout.
- **Header:** Creates a black header bar with a centered white title.

---

####
<a name="chouse-mode"></a> `Chouse_Mode` Section
```css
.Chouse_Mode {
    margin-top: 120px;
    display: block;
}
.Chouse_Mode button {
    height: 40px;
    width: 200px;
    margin-left: 35px;
    border: 0;
    border-radius: 40px;
    background: rgb(214, 231, 230);
    font-family: Arial, Helvetica, sans-serif;
    font-size: 20px;
    transition: background, 0.5s, ease-in-out;
    color: rgb(65, 66, 54);
}
.Chouse_Mode .active_button {
    background: rgb(176, 231, 228);
}
```
- **Purpose:** Styles the mode selection buttons with a rounded design and smooth background transition effect.

---

####
<a name="autodocconfig-yml"></a>
## `autodocconfig.yml` - Auto Documentation Configuration

This file defines the settings for generating automated documentation for the project. It specifies the project name, language, files to ignore, and other build configurations.

---

### Key Configuration Parameters

#### Project Metadata
| Parameter         | Value          | Description                          |
|-------------------|----------------|--------------------------------------|
| `project_name`    | `"Project"`    | The name of the project.             |
| `language`        | `"en"`         | Language for the documentation.      |

---

#### Ignored Files
The following files and directories are excluded from the documentation generation process:
- Python bytecode and cache files (`*.pyc`, `*.pyo`, `__pycache__`, etc.).
- Virtual environments (`venv`, `env`, etc.).
- IDE settings (`.vscode`, `.idea`, etc.).
- Logs and coverage reports (`*.log`, `.coverage`, etc.).
- Version control files (`.git`, `.gitignore`, etc.).
- Miscellaneous files (`*.pdb`, `*.md`, etc.).

---

#### Build Settings
| Parameter         | Value          | Description                          |
|-------------------|----------------|--------------------------------------|
| `save_logs`       | `false`        | Disables saving logs during build.   |
| `log_level`       | `2`            | Sets the verbosity of logging.       |

---

#### Structure Settings
| Parameter                  | Value   | Description                          |
|----------------------------|---------|--------------------------------------|
| `include_intro_links`      | `true`  | Includes links in the introduction.  |
| `include_intro_text`       | `true`  | Includes introductory text.          |
| `include_order`            | `true`  | Maintains order of documentation.    |
| `use_global_file`          | `true`  | Uses a global file for settings.     |
| `max_doc_part_size`        | `5000`  | Maximum size for each doc section.   |

---

### Key Notes
> - The `ignore_files` section ensures that unnecessary files are excluded from the documentation process, improving clarity and reducing clutter.
> - The `build_settings` and `structure_settings` provide flexibility in customizing the output format and behavior of the auto-documentation tool.

---
<a name="requirements-txt"></a> 
## `requirements.txt` - Project Dependencies

This file lists all the Python libraries and their versions required for the project to run.

---

### Dependencies
| Library         | Version | Description                                    |
|------------------|---------|------------------------------------------------|
| `colorama`      | 0.4.6   | Cross-platform colored terminal text output.   |
| `Eel`           | 0.17.0  | For Python-JavaScript communication in UI.     |
| `Flask`         | 3.1.0   | Web framework used for building the server.    |
| `pytest`        | 8.3.3   | Testing framework for unit tests.              |
| `Requests`      | 2.32.3  | Simplifies HTTP requests in Python.            |

---

### Key Notes
> - Ensure all dependencies are installed using `pip install -r requirements.txt` before running the project.
> - The specified versions ensure compatibility and stability of the system.


markdown
<a name="test-to-work"></a> `test_to_work() -> int`
**Purpose:** Returns a static integer value.

**Logic Flow:**
- Returns the integer `10`.

**Data Contract:**
| Entity   | Type      | Role                  | Notes                                       |
|----------|-----------|-----------------------|---------------------------------------------|
| `result` | `int`     | Output                | Returns the integer value `10`.             |


markdown

    