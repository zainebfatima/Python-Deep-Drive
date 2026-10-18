Lab 16: Virtual Environments (venv)

Objective

- Understand the purpose and benefits of using virtual environments in Python.
- Learn to create, activate, and deactivate a virtual environment.
- Practice installing Python packages within a virtual environment.
- Recognize how virtual environments help maintain project dependencies and isolation.

---

What is a Virtual Environment?

A virtual environment is a separate Python environment created for a specific project.

It allows each project to have its own Python packages and package versions without interfering with other projects.

Simple idea:

Project A → its own environment → its own packages
Project B → its own environment → its own packages

A virtual environment is stored as a folder inside the project.

---

Step 1: Create a Project Folder

mkdir lab16_venv
cd lab16_venv

The project folder was created and entered successfully.

---

Step 2: Create a Virtual Environment

Initially, creating the environment failed because the Ubuntu system was missing the "python3.12-venv" package.

The package was installed using:

sudo apt update
sudo apt install python3.12-venv

After that, the virtual environment was successfully created:

python3 -m venv venv

The "venv" folder was created inside the project folder.

---

Step 3: Activate the Virtual Environment

source venv/bin/activate

After activation, "(venv)" appeared at the beginning of the terminal prompt.

This indicates that the terminal is now using the virtual environment.

---

Step 4: Check pip

pip --version

Output showed that pip was located inside the virtual environment:

/home/ubuntu/lab16_venv/venv/lib/python3.12/site-packages/pip

This confirmed that pip was being used from the virtual environment.

---

Step 5: Install a Python Package

The "requests" package was installed as a practical example:

pip install requests

It was successfully installed along with its dependencies.

The installation location was:

/home/ubuntu/lab16_venv/venv/lib/python3.12/site-packages

This demonstrated that packages installed while the virtual environment is active are stored inside that environment.

---

Step 6: Check Package Isolation

Outside the virtual environment, the system Python found "requests" at:

/usr/lib/python3/dist-packages/requests/_init_.py

Inside the virtual environment, it found "requests" at:

/home/ubuntu/lab16_venv/venv/lib/python3.12/site-packages/requests/_init_.py

The different locations demonstrated that the virtual environment has its own package location.

---

Step 7: Deactivate the Virtual Environment

deactivate

After running the command, "(venv)" disappeared from the terminal prompt.

The virtual environment was not deleted. It remains stored inside:

/home/ubuntu/lab16_venv/venv

It can be activated again whenever the project needs it:

source venv/bin/activate

---

Key Learning

A virtual environment provides an isolated Python workspace for a project.

- "venv" creates the environment.
- "activate" starts using the environment.
- "pip" installs packages into the active environment.
- "deactivate" leaves the environment.
- The environment remains stored as a folder and can be used again later.

Simple Analogy

A virtual environment is like giving each Python project its own room.

Project A
└── venv
    └── its own packages

Project B
└── venv
    └── its own packages

Packages installed in one project's virtual environment do not automatically become part of another project's virtual environment.

---

Commands Practiced

mkdir lab16_venv
cd lab16_venv
sudo apt update
sudo apt install python3.12-venv
python3 -m venv venv
source venv/bin/activate
pip --version
pip install requests
pip show requests
which python
which pip
python3 -c "import requests; print(requests._file_)"
deactivate

Result

Successfully created, activated, used, tested, and deactivated a Python virtual environment.

Lab 16 completed successfully.
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/89aa8db2-9a6c-4798-ad2a-28ad4d5d8548" />
