## Usage

After installation teached in README.md you will have a folder structure similar to this:

```bash
qastronaut/
│
├── config
│   ├── api_key.json
│   ├── requests
│   │   └── curl.txt
│   ├── requests_names
│   │   └── user_requests.txt
│   └── tests
│       ├── body
│       │   ├── empty
│       │   ├── invalid
│       │   ├── nonexistent
│       │   ├── null
│       │   └── size
│       └── params
│           ├── empty
│           ├── invalid
│           ├── nonexistent
│           ├── null
│           └── size
│
├── functions/
│
├── images/
│
├── unit_tests/
│
├── qastronaut.py
├── README.md
├── requirements.txt
└── LICENSE 
```

**Remember**: The API Key is an essential component for QAstronaut to function properly. If you've changed it or didn't provide it during installation, it's important to update the `api_key.json` file with a valid key.

## Test and Scenario Configuration

All interaction with QAstronaut is done via command line for execution. At the configuration point, we will focus on the `config/` directory.

### Adding an endpoint for test

To include an endpoint, follow the procedure below:

1. Save the cURL of the desired request and paste it into a file named `curl.txt`.
2. `curl.txt` is located in the `config/requests/` directory.

This ensures proper configuration for API endpoints test in your testing environment.

> Currently, QAstronaut is only capable of testing one endpoint at a time. If you need to test multiple endpoints, you will need to replace the curl.txt file each time.

### Test Configuration

In the `config/tests/` directory, you'll find all the JavaScript test scripts available for QAstronaut, for each test scenario that QAstronaut is capable of creating. It is essential to note that this list of tests is constantly evolving and requires changes to fit the requirements of the planned endpoint. Be sure to keep these scripts up-to-date to ensure adequate testing coverage.

Alternatively, you have the option to create your test script for the scenarios listed in the tests folder, overwriting the existing ones. This approach allows for complete customization according to your specific needs.

> QAstronaut's test configuration refers to the [Tests](https://learning.postman.com/docs/getting-started/first-steps/write-your-first-test/) element in Postman.

>**Obs:** In terms of the number of test scenarios available, QAstronaut is committed to continuous improvement by expanding its repertoire of test heuristics and broadening the scope of API testing. We are constantly working to offer a greater variety of test scenarios and enhance the overall test coverage, ensuring that QAstronaut remains a valuable tool for comprehensive API testing.

> **Remember:** Other project directories, such as `functions/`, are folders linked to the operation of QAstronaut. Any changes or deletions will directly affect its operation.

### Parameterizing Test Scenario Titles

In QAstronaut, the names of [Requests](https://learning.postman.com/docs/sending-requests/requests/) are defined as follows:

```text
CT000 - JSON Field - Scenario - user_requests
```

1. "CT000" represents a unique counter for each test scenario.
2. "user_requests" is the name of the file that should be customized to identify the test suite. 
> **Attention:** Ensure that you fill in the `user_requests` file because QAstronaut relies on it to function correctly, and it can be found in the `config/requests_names/` directory.
3. The "JSON Field" refers to the field being tested in the test scenario.
4. The "Scenario" describes the actual test scenario, such as "Non-existent," "Empty," "Null," and so forth.

For a practical example, a real request name can be defined as follows:

```text
CT023 - Account - Empty - RegisterUser
```

This naming structure allows for easy identification and tracking of test scenarios, helping to keep your test project organized and efficient.

## Creating Test Suites

Once the `curl.txt` file has been created and placed in the `config/requests/` directory, you are ready to run QAstronaut. Follow these steps:

1. Navigate to the `qastronaut/` directory, which contains the `qastronaut.py`

 file.
2. Execute the following command:

```bash
python qastronaut.py
```

> **Note:** In some cases, you may need to use `python3` or `py` instead of `python` to invoke the Python 3 interpreter.

3. You will receive the following instructions:

```bash
Please place the cURL command in a text file named 'curl.txt' and press 'Enter'.

Did you place the cURL command in 'curl.txt'? (Y/n): 
```

4. If you have already added the `curl.txt` file, press Enter to proceed. Otherwise, add the `curl.txt` file and continue.

5. After this step, you will be prompted to provide the name of the collection that will be created for the test suite and the folder name:

```bash
What will be the name of the collection? Test
What will be the name of the folder? Test

Collection 'Test' created successfully with the collection ID: 23485401-2e399297-2c19-41b1-b1ee-a3f209bfee97

Folder 'Test' created successfully with the folder ID: 156a5f3f-a018-1943-1373-ba635b2fad44
```

6. After QAstronaut confirms the successful creation of the collection and folder, the next step is to inform the desired HTTP method:

```bash
Which HTTP method do you want to use (GET/POST/PUT/DELETE, etc.)? post
```

7. After choosing the method, QAstronaut will show a summary of the API endpoint that will be tested and will ask if it can proceed.

```bash
Request Method: POST
Request URL: https://serverest.dev/produtos
Request Body: {'name': 'Cheese IV', 'price': 524}
Request Headers: Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6IkFteTg0QGhvdG1haWwuY29tIiwicGFzc3dvcmQiOiJJTUlVQmpOU1hKSnSv8AAxsOn1LBfU1dBQn38x8nDSHnJvCs9bUeV2y3Ynu1pa9wRa3B06XDvDYxQjwzx4T6Y1sAt30raXnu3wsDDjx36tvZBjc1S2gjEDGvDD Al7eSvA1xG3k7Nk6A
Content-Type: application/json

Can I run? (Y/n): Y

-------------------------------

<Response [200]>
name has been tested empty
<Response [200]>
price has been tested empty
...
```

8. Once that is done, QAstronaut will show the corresponding HTTP request and start creating tests in the Postman workspace, providing feedback for each created HTTP request.

Now you've performed your first API test using QAstronaut, if you have any questions, don't hesitate to visit the [Troubleshooting](Troubleshooting) section on this Wiki.