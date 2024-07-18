### Issues with the API Key

#### Expired API Key
If your API Key has expired, QAstronaut won't be able to create tests in Postman. To resolve this issue:

1. Generate a new API Key in Postman.
2. Update the `api_key.json` file in the `config/` directory with the new API Key.

#### Deleted API Key
If the saved API Key has been deleted, QAstronaut won't be able to access Postman. To fix this:

1. Generate a new API Key in Postman.
2. Update the `api_key.json` file in the `config/` directory with the new API Key.

### Status Code Errors When Creating Requests, Folders, or Collections

#### Status Code 401 (Unauthorized)
This error is often related to issues with the API Key. It means the request requires user authentication. To resolve this:

1. Ensure your API Key is valid and correctly included in the request headers.
2. If necessary, generate a new API Key in Postman and update the `api_key.json` file in the `config/` directory.

#### Status Code 403 (Forbidden)
This error can occur if you have exceeded the free API call limits on Postman. To resolve this:

1. Upgrade your Postman account to a plan with higher limits.
2. Check your usage limits with the [Postman resource usage page](https://learning.postman.com/docs/developer/postman-api/postman-api-rate-limits/).

#### Status Code 404 (Not Found)
This error indicates no internet connection. To resolve this:

1. Check your internet connection to ensure it is working properly.
2. Try again after restoring the connection.

#### Other Status Codes
If you encounter other status codes, it might be an issue with the API endpoint or the request configuration. Here are some common status codes and their meanings:

- **400 Bad Request:** The server could not understand the request due to invalid syntax.
  - **Solution:** If QAstronaut is receiving this code, it might be due to an unexpected change in the Postman API. Contact the QAstronaut team and wait for a resolution.

- **500 Internal Server Error:** The server encountered an unexpected condition that prevented it from fulfilling the request.
  - **Solution:** Check the availability of the Postman service.

---

If you encounter other issues or need additional help, don't hesitate to report the problem by creating an issue in our [GitHub Issues](https://github.com/QAstronaut/qastronaut/issues) page. This will help us improve QAstronaut and assist you better.