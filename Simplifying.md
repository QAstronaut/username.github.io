QAstronaut is a tool designed to make API testing easier by automatically generating test scenarios in Postman. Here's a simple breakdown of what it does and how to use it:

### What QAstronaut Does

QAstronaut helps you test your API endpoints by:
1. Taking a cURL command that you provide.
2. Creating a set of predefined test scenarios based on that cURL command.
3. Generating these tests in Postman, a popular tool for API testing.

The following diagram illustrates this process:

![QAstronaut_simple.jpg…](https://github.com/QAstronaut/qastronaut/blob/main/images/QAstronaut_simple.jpg)

### How to Use QAstronaut

1. **Setup Your Environment:**
   - Follow the instructions in the `README.md` to set up QAstronaut.
   - Make sure your folder structure looks like this:

    ```bash
    qastronaut/
    ├── config/
    ├── functions/
    ├── images/
    ├── unit_tests/
    ├── qastronaut.py
    ├── README.md
    ├── requirements.txt
    └── LICENSE 
    ```

2. **Add Your API Key:**
   - Update the `api_key.json` file in the `config/` directory with your Postman API key. This key is essential for QAstronaut to create tests in Postman.

3. **Prepare Your cURL Command:**
   - Save the cURL command of the API endpoint you want to test in a file named `curl.txt`.
   - Place this file in the `config/requests/` directory.

4. **Customize Your Test Scenario Names:**
   - Edit the `user_requests.txt` file in the `config/requests_names/` directory to identify your test suite.
   - Test scenario names follow this format: `CT000 - JSON Field - Scenario - user_requests`. Customize it as needed.

5. **Run QAstronaut:**
   - Navigate to the `qastronaut/` directory.
   - Run the script by executing `python qastronaut.py` (or `python3 qastronaut.py` depending on your setup).

6. **Follow the Prompts:**
   - Provide the required information such as the name of the collection, folder, and the HTTP method.
   - QAstronaut will confirm the details and ask for your permission to proceed.
   - It will then create and run the tests in your Postman workspace, providing feedback for each test scenario.

### Summary

In essence, QAstronaut simplifies the process of API testing by:
- Automating the generation of test scenarios.
- Integrating seamlessly with Postman.
- Providing a straightforward setup and execution process.

By using QAstronaut, you can ensure comprehensive testing of your API endpoints with minimal manual effort.