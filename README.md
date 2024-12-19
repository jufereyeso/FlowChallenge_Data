Some recomendations for the challenge

### Step 1: Install Python
Make sure you have Python installed on your machine. You can download it from [python.org](https://www.python.org/downloads/).

### Step 2: Create a Virtual Environment

1. **Open your terminal (Command Prompt, PowerShell, or Terminal)**.
   
2. **Navigate to your project directory** where you want to create the virtual environment. Use the `cd` command:
   ```bash
   cd path/to/your/project
   ```

3. **Create the virtual environment**. You can do this using the following command:
   ```bash
   python -m venv venv 
   # or 
   python3 -m venv venv
   ```
   This will create a new directory named `venv` in your project folder, which contains the virtual environment.

### Step 3: Activate the Virtual Environment

- **On Windows**:
  ```bash
  venv\Scripts\activate
  ```

- **On macOS and Linux**:
  ```bash
  source venv/bin/activate
  ```

After activation, your terminal prompt should change to indicate that the virtual environment is active, usually by prefixing the prompt with `(venv)`.

### Step 4: Install Libraries from a requirements.txt file

1. **Make sure you have a `requirements.txt` file** in your project directory. This file should list all the libraries you want to install, each on a new line, for example:
   ```
   numpy==1.21.2
   pandas==1.3.3
   requests==2.26.0
   ```

2. **Install the libraries using pip**:
   ```bash
   pip install -r requirements.txt
   ```

### Step 5: Deactivate the Virtual Environment (when done)

When you are finished working in the virtual environment, you can deactivate it by simply running:
```bash
deactivate
```

### Summary of Commands
```bash
# Step 1: Navigate to your project directory
cd path/to/your/project

# Step 2: Create a virtual environment
python -m venv venv

# Step 3: Activate the virtual environment
# Windows
venv\Scripts\activate
# macOS/Linux
source venv/bin/activate

# Step 4: Install libraries from requirements.txt
pip install -r requirements.txt

# Step 5: Deactivate the virtual environment
deactivate
```

You are now ready to work within your virtual environment! If you have any questions or need further assistance, feel free to ask.
