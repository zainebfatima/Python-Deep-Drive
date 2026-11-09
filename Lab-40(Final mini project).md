Python Deep Dive — Lab 40

Final Mini-Project: Building a CLI Data Processor

Status: Completed
Score: 100/100
Environment: Ubuntu 24.04
Python: 3.12
Virtual Environment: "lab40_env"

1. Objectives

- Fetch data from an API using Python.
- Save JSON data into a file.
- Implement command-line arguments using "argparse".
- Integrate logging.
- Handle exceptions.
- Validate JSON data structures.

2. Concepts Practiced

Concept| Purpose
"requests"| Fetch API data
"response.raise_for_status()"| Handle unsuccessful HTTP responses
"response.json()"| Convert JSON response into Python data
"json.dump()"| Write JSON data into a file
"json.load()"| Read JSON data from a file
"argparse"| Accept command-line arguments
"logging"| Record program events and errors
"try-except"| Handle exceptions
"isinstance()"| Validate Python data types
"main()"| Connect the program functions

3. Project Structure

lab40/
│
├── data_processor.py
├── output.json
├── copied_output.json
└── lab40_env/

4. Program Features

The CLI Data Processor supports:

- Fetching JSON data through an API URL.
- Reading JSON data from an existing file.
- Saving processed data to an output file.
- Choosing an output filename through CLI arguments.
- Logging successful operations and errors.
- Validating that data is a dictionary or list.

5. Example Commands

Fetch API data:

python data_processor.py --url https://jsonplaceholder.typicode.com/todos/1

Read an existing JSON file:

python data_processor.py --file output.json --output copied_output.json

6. Errors Encountered and Fixed

- Corrected a syntax error in the "_name_" condition.
- Fixed a misspelled "args.url" variable.
- Corrected the missing-input handling in "main()".
- Resolved code formatting and spacing issues during development.

7. Testing

- API fetching: Successful.
- JSON file creation: Successful.
- Saved JSON content: Verified.
- Invalid CLI input: Tested; error logged without a traceback.
- Lab assessment: 100/100.

8. Final Learning Outcome

Completed a Python command-line application by combining API requests, JSON processing, argument parsing, logging, exception handling, and data validation.

Python Deep Dive: 40 Labs Completed.

Alhamdulillah! A major milestone in my cybersecurity learning journey.
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/9324f7d9-08c7-4eec-bc35-c75f253d3755" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/3d41821d-b398-4d13-a8b1-7d3a5314e1f5" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/f998bdfb-14b4-42c1-b7ea-f63fbb5ffdf6" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/47fa6b0b-4c34-4fae-b046-739945e866d7" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/3993b41d-b7d8-4530-a21f-3d30c6a3cd46" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/1491b83b-3869-4558-abd2-996e75c23893" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/6324e3af-02c0-492e-839c-c1710168903a" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/1354dbd0-8810-4a0a-9a69-8187a5e44e47" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/26d03bd4-2dbb-485f-8e23-a1aee86f1086" />








