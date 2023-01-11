# Best Practice for Cypress Web Testing: Adding Intermediate Assertions

> This text was produced by ChatGPT with co-authorship by Walmyr Lima and Silva Filho.

___

As a web developer or QA tester, you're likely familiar with using Cypress to automate your web testing. One best practice that can make your tests more robust and user-friendly is adding intermediate assertions between getting elements and interacting with them.

For example, let's say you want to test a login form where the user enters a password. Instead of writing a test like this:

```js
cy.get('input[type="password"]').type('53cR37p@s5W0rd!')

```

You could add an intermediate assertion to check that the password input is visible before attempting to type in it:

```js
cy.get('input[type="password"]').should('be.visible').type('53cR37p@s5W0rd!')

```

This may seem like a small difference, but it can make a big impact on the reliability and usability of your tests.

One major benefit of adding these intermediate assertions is that they make your tests closer to how a real user would interact with your app. For example, if the password input is not visible (e.g. due to a styling issue or an incorrect DOM structure), a real user would not be able to enter a password. But without the intermediate assertion, Cypress would still attempt to type in the input, even though it's not visible. This could lead to unpredictable and unreliable test results.

Another benefit is that adding these intermediate assertions can help you catch subtle bugs in your app. For example, if the password input is present in the DOM but is hidden by CSS, Cypress would still be able to interact with it. But with the assertion, Cypress will fail the test and alert you that the password input is not visible. This can help you identify and fix these types of bugs before they affect real users.

In summary, adding intermediate assertions between getting elements and interacting with them in Cypress web testing is a best practice that can help you write more robust and user-friendly tests. It can also help you identify and fix subtle bugs in your app. So, next time you're writing a Cypress test, consider adding some intermediate assertions to make your test closer to how a real user would interact with your app.
