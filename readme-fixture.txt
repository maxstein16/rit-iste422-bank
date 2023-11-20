## Bank Testing

#### CSV Test Running

If in project root directory:

Windows: ```gradle runCheckingFixture --args="-f src/test/resources/CheckingAccountTest.csv"``` or ```gradle runSavingsFixture --args="-f src/test/resources/SavingsAccountTest.csv"```

Mac/Linux: ```./gradlew runCheckingFixture --args="-f src/test/resources/CheckingAccountTest.csv``` or ```./gradlew runSavingsFixture --args="-f src/test/resources/SavingsAccountTest.csv```

---

#### Fixtures

If in project root directory:

Windows: ```gradle runCheckingFixture``` or ```gradle runSavingsFixture```

Mac/Linux: ```./gradlew runCheckingFixture ``` or ```./gradlew runSavingsFixture```

---

### Untestable scenarios

One untestable scenario arises when I read test scenarios from an external CSV file (specified by TEST_FILE). 
While the code successfully loads scenarios from this file, it does not validate the content of the file itself. 
Therefore, if the file contains incorrect or unexpected data, the tester does not have the capability to detect and report these issues. 
This limitation makes it challenging to ensure the correctness of the external file's content during testing.

Although the code provides the option to specify a single test scenario on the command line using a file argument, it lacks comprehensive support for running and managing test scenarios through command-line parameters. 
For instance, I do not have the functionality to specify and execute a specific test case or group of test cases directly from the command line. 
This limitation restricts the flexibility and convenience of command-line testing for specific scenarios.

The tester does not support parallel test execution, meaning that it runs test scenarios sequentially. 
In scenarios with a large number of tests, parallel execution could significantly reduce testing time. 
The absence of this feature limits the efficiency of the testing process, particularly for large test suites.