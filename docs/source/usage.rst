Usage
=====

Installation
------------

1. **Clone the Repository**

   First, clone this repository to your local machine using Git:

   ```bash
   git clone [<repository-url>](https://github.com/PennyWiseApp/PennyWise.git)
   cd PennyWise
   ```

2. **Run npm Install**

   Within the root directory of the project, run the following command:

   ```bash
   npm install
   ```

   This command does several things:

   - Installs the Node.js dependencies listed in `package.json`.
   - Automatically triggers the `postinstall` script, which sets up the Python virtual environment (`venv`) within the `backend/` directory and installs the Python dependencies specified in `backend/requirements.txt`.

   **Note:** The `postinstall` script specifically does the following:

   - Creates a Python virtual environment in `backend/venv`.
   - Activates the virtual environment.
   - Uses `pip` to install the Python packages listed in `backend/requirements.txt`.

Registering/Logging In
----------------------

To register or login you can use the respective ``register()`` and ``login()`` functions. These will use POST requests to check the login details against the database.

Assuming a successful login, the user's categories, transactions and budget will be loaded.

Category Management
-------------------

The ``addCategory()``, ``fetchCategories()`` and ``deleteCategory()`` functions handle the creation, reading and deletion of user-created categories.

After a category is added or deleted, ``fetchCategories()`` is called to update the UI and ensure that the changes are shown to the user.

Transaction Management
----------------------

Transaction management is handled the same as category management. Each time a transaction is added or deleted, a fetch function is called to present the changes to the user.

Budget Creation
---------------

The ``calculateBudget()`` function is called on start to create the initial budget. Once this exists, ``fetchBudget()`` is called to update the information shown to the user each time a change is made to the budget.

``fetchBudget()`` also updates any goals set with the ``setGoal()`` function which, like ``login()`` and ``register()`` uses POST requests sent to the server to update the data.

