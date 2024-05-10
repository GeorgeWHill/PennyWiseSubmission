Usage
=====

.. _installation:

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

Creating recipes
----------------

To retrieve a list of random ingredients,
you can use the ``lumache.get_random_ingredients()`` function:

.. autofunction:: lumache.get_random_ingredients

The ``kind`` parameter should be either ``"meat"``, ``"fish"``,
or ``"veggies"``. Otherwise, :py:func:`lumache.get_random_ingredients`
will raise an exception.

.. autoexception:: lumache.InvalidKindError

For example:

>>> import lumache
>>> lumache.get_random_ingredients()
['shells', 'gorgonzola', 'parsley']

