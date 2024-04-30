# playwright-sample-project

## **Overview:**

This is a sample Automation project using Playwright and Typescript and uses playwright-testrunner to execute test cases. This is a Data Driven framework focused on separating the test scripts logic and the test data from each other. This allows us to create test automation scripts by passing different sets of test data. The test data set is kept in an external Excel Sheet. The test scripts connect to the external Excel sheet to get the test data. This framework significantly reduces the number of test scripts compared to a modular based framework when we need to test for multiple sets of data for same functionality.

For Demo purpose UI test cases are created on [advantageonlineshopping.com](http://advantageonlineshopping.com/) site and API test cases are created on these [SOAP API](https://www.advantageonlineshopping.com/accountservice/ws/accountservice.wsdl) & [REST API](https://fakestoreapi.com) endpoints.

## Features

- Test data is stored in an Excel sheet and from this Excel sheet user can control the test cases that needs to be run.
- User also has full control to run test in different modes from the Excel sheet.

- Has utility built in for file download, Read PDF files etc.
- Generates Playwright's HTML Report, Allure Report & JUnit Report in HTML format for each exaction. 
- Allure & Playwright report including snapshots and video in case of test failure.
- Test execution logs are captured in the log file.
- You Can execute local tests in Playwright's UI Mode
- All config is controlled by playwright config file.

#### Supported Browsers
1. Chrome - default browser
2. Firefox
3. MS Edge
4. WebKit - web browser engine used by Safari

#### Run Mode Details
| Mode | Execl Value |Description |
| ------ | ------ | ------ |
|Normal|Blank| 	Runs the tests sequentially|
|Serial|serial| 	Runs the tests sequentially. On test failure, all subsequent tests are skipped|
|Parallel|parallel| 	Runs the tests parallelly, this is ideal when tests in the scenario are independent of one another|

#### Steps to use
##### 1. Installation

Playwright framework requires [Node.js](https://nodejs.org/) v14+ to run.

The Playwright framework requires Node.js v14+ to run.
Code from GitHub needs to be downloaded: https://github.com/Mano-labs/Rakevet-Israel.git


installing the playwright: 
npm init playwright@latest

Installing the dependencies.
```sh
npm ci
```
##### 2. Test creation
- Create Test file with extenstion .spec.ts. Eg LoginTest.spec.ts
- In the testData excel create a sheet with name of test. Eg. LoginTest
- Create a execution sheet and make an entry of new test case. Eg. in the Regression sheet add a row for new test LoginTest and update other columns like run, mode etc.

##### 3. Execution
To run test suite use below command.
```
$env:TEST_NAME="RESTUserTest"; npm run local:test
```
**Note:** Replace RESTUserTest with the name of your test file (without the .spec.ts extension).

To run individual test locally use below command.
```
$env:TEST_NAME="LogInTest"; npm run local:test:ui
```

To change any environment configuration in .env file at run time use set command.
Eg: To change browser to MS Edge use below command

```
$env:BROWSER="edge"
```
A similar command can be used to update other environment configuration

To show the Allure report use the below command
```
npx playwright show-report test-results\report
```

##### Setting up the path for Excel : 
1. locate the src/utils
2. Locate the TEST_PATH and SUITE_PATH
3. Replace the relative paths (TEST_PATH  & SUITE_PATH) with the absolute path to the data folder

Should look like this: 
```
export default class ExcelConstants {
    static readonly TEST_PATH = 'C:/Users/User/Documents/Playwright/playwright-sample-project/src/resources/data/testData.xlsx';
    static readonly SUITE_PATH = 'C:/Users/User/Documents/Playwright/playwright-sample-project/src/resources/data/testData.xlsx';
    static readonly YES = "YES"
}
```

##### 4. Report & Logs
Open a file explorer or a terminal/command prompt and navigate to the test-results/results/ directory within your project.
Locate the index.html file in this directory.

=======
# Rakevet-Israel
>>>>>>> 2284489943a5bafa48485b352cd5bee0a614b5e7
