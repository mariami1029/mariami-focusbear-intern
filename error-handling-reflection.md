# Testing Error Handling & Edge Cases — QA Reflection

## 1. Boundary Value Analysis

Boundary Value Analysis (BVA) is a test design technique that focuses on values at the boundaries of an input range.

Defects often occur at the edges of valid and invalid ranges, so instead of testing only normal values, QA should test values around the boundaries.

For example, if a field accepts values from 1 to 100, useful test values are:

* 0 — below the minimum
* 1 — minimum valid value
* 2 — just above the minimum
* 99 — just below the maximum
* 100 — maximum valid value
* 101 — above the maximum

BVA helps reduce the number of test cases while still targeting areas where defects are more likely to occur.

It is especially useful for:

* Numeric fields
* Character limits
* Password length requirements
* Date ranges
* File size limits
* Task durations
* Quantity limits

---

## 2. Common Edge Cases

Edge cases are unusual or extreme situations that may expose unexpected behavior.

### Forms

For forms, I would test:

* Empty fields
* Minimum allowed input
* Maximum allowed input
* Input just below the minimum
* Input just above the maximum
* Very long text
* Spaces only
* Leading and trailing spaces
* Special characters
* Unicode characters
* Invalid formats
* Duplicate values
* Copy-pasted input
* Unexpected characters
* Rapidly clicking Submit
* Submitting the form multiple times

### Authentication

For login and authentication, I would test:

* Empty email and password
* Invalid email format
* Incorrect password
* Very long credentials
* Leading/trailing spaces
* Case sensitivity
* Expired sessions
* Invalid or expired reset links
* Multiple failed login attempts
* Login during network interruption
* Logout and immediate re-login
* Multiple sessions or devices

### Application Flows

For general application flows, I would test:

* Refreshing the page during an operation
* Closing the application during an operation
* Navigating away before saving
* Double-clicking buttons
* Using the browser Back/Forward buttons
* Performing actions in an unexpected order
* Repeating the same action quickly
* Using the application with incomplete data
* Losing network connectivity during an operation

---

## 3. Testing Network Failures and Offline Mode

Network instability can cause unexpected problems when an application depends on APIs or cloud services.

QA should test different network conditions instead of only testing with a stable high-speed connection.

### Useful Network Scenarios

I would test:

* Normal connection
* Slow connection
* High latency
* Temporary connection loss
* Complete offline mode
* Connection restored after failure
* Intermittent connection
* Request timeout
* Failed API request

For a web application, Chrome DevTools can be used to simulate different network conditions.

### Expected Behavior

When a network request fails, the application should:

* Inform the user clearly
* Avoid showing misleading success messages
* Prevent accidental duplicate submissions
* Preserve user-entered information when possible
* Handle timeouts gracefully
* Allow the user to retry when appropriate
* Recover when the connection is restored
* Avoid corrupting or duplicating data

---

## 4. Unexpected Input and Invalid Data

Applications should never assume that users will always provide expected input.

QA should test invalid, unexpected, and unusual data to verify that the application handles it safely and predictably.

Examples include:

* Invalid data types
* Extremely long strings
* Empty values
* Null or missing values
* Special characters
* Unicode characters
* Incorrect date formats
* Negative numbers where they are not allowed
* Extremely large numbers
* Duplicate records
* Malformed API responses

The expected behavior should be graceful failure rather than a crash or corrupted state.

The application should validate input and provide a clear explanation of what the user needs to correct.

---

## 5. Testing Error Messages

Error messages should help users understand what happened and what they can do next.

A good error message should be:

### Clear

The user should understand the problem without needing technical knowledge.

### Specific

The message should explain what went wrong rather than simply saying "Error."

### Actionable

When possible, it should tell the user how to fix the problem.

### Consistent

Similar errors should use consistent terminology throughout the application.

### Non-Technical

Users generally should not see unnecessary stack traces, internal errors, database information, or technical implementation details.

For example, instead of:

> Error 500

a more useful message could be:

> Something went wrong while saving your task. Please try again.

QA should also verify that error messages:

* Appear in the correct location
* Are readable
* Do not disappear too quickly
* Are associated with the correct field/action
* Do not cover important UI elements
* Are accessible where appropriate
* Do not appear when an operation actually succeeds

---

## 6. Edge Cases in Focus Bear's Onboarding Flow

Several edge cases could potentially affect a Focus Bear onboarding or first-time-user flow.

I would specifically investigate:

### Account Creation

* Empty required fields
* Invalid email format
* Already registered email
* Very long name
* Special characters in names
* Password at the minimum allowed length
* Password below the minimum length
* Weak passwords
* Password confirmation mismatch
* Spaces in credentials
* Network failure during registration

### Login

* Incorrect credentials
* Empty credentials
* Repeated failed attempts
* Login with an unverified account, if verification is required
* Network interruption during login
* Expired authentication session

### First-Time Setup

* Closing the application during setup
* Refreshing during setup
* Skipping a required step
* Going back to a previous step
* Completing steps in an unexpected order
* Very slow network during setup
* Losing connection while saving preferences
* Restarting the application midway through onboarding

### Initial Data

* No existing tasks or habits
* Very large initial dataset
* Invalid or incomplete data
* Duplicate data
* Missing optional information

The goal would be to determine whether onboarding can recover from unexpected situations without losing progress or leaving the user in an unusable state.

---

## 7. If the App Fails Midway Through a Critical Action

If the application fails while performing a critical action, it should fail safely and preserve data integrity.

For example, imagine a user is creating an important task and the application loses connection while saving it.

The application should:

1. Avoid falsely telling the user that the task was saved.
2. Preserve the user's input whenever possible.
3. Clearly indicate that the operation was unsuccessful or is still processing.
4. Prevent accidental duplicate submissions.
5. Allow the user to retry when appropriate.
6. Verify the final state before displaying success.
7. Recover gracefully when the connection returns.

QA should verify both the immediate behavior and the final data state.

For example, after retrying an operation, I would check whether:

* Exactly one record was created
* No partial or corrupted record exists
* The user can continue normally
* The UI reflects the correct state
* The operation can safely be repeated if necessary

For critical actions, maintaining data integrity is more important than simply displaying a fast response.

---

## 8. Testing Network Instability

To test network instability, I would create controlled scenarios using network throttling and temporary connection interruptions.

### Scenario 1 — Slow Connection

I would:

1. Enable network throttling.
2. Open Focus Bear.
3. Perform important workflows.
4. Observe loading times and UI responsiveness.
5. Check whether loading states are displayed correctly.

### Scenario 2 — Connection Lost During an Action

I would:

1. Start an important operation.
2. Disable the network connection during the request.
3. Observe the application behavior.
4. Check whether an appropriate error is shown.
5. Restore the connection.
6. Retry the operation.
7. Verify that the final data state is correct.

### Scenario 3 — Intermittent Connection

I would repeatedly switch between connected and disconnected states while performing actions.

I would check whether the application:

* Recovers correctly
* Avoids duplicate requests
* Preserves user input
* Shows accurate status information
* Allows safe retries
* Avoids crashes
* Keeps the UI consistent with the server state

---

## 9. Example Edge-Case Test Matrix

| Area          | Normal Case         | Boundary / Edge Case        | Expected Result                    |
| ------------- | ------------------- | --------------------------- | ---------------------------------- |
| Registration  | Valid email         | Invalid email format        | Clear validation message           |
| Password      | Valid password      | Minimum length              | Accepted if requirements are met   |
| Password      | Valid password      | One character below minimum | Rejected with clear message        |
| Task creation | Normal task         | Very long task name         | Handled without UI breakage        |
| Task creation | Saved task          | Network lost during save    | No false success or duplicate data |
| Login         | Correct credentials | Incorrect password          | Clear authentication error         |
| Navigation    | Normal navigation   | Refresh during save         | Data remains consistent            |
| Network       | Stable connection   | Temporary disconnection     | Graceful error and recovery        |
| Form          | Valid input         | Empty required field        | Validation message                 |
| API           | Valid response      | Malformed/failed response   | Graceful error handling            |

---

## 10. Personal Reflection

As a QA tester, I should not test only the most common user journey. Users can provide unexpected inputs, lose their internet connection, click buttons repeatedly, close the application at the wrong moment, or encounter unexpected system conditions.

Boundary Value Analysis is useful because it helps identify defects around the limits of accepted values.

For Focus Bear's onboarding flow, I would pay particular attention to registration, authentication, incomplete setup, network interruptions, invalid input, and restarting the application during important operations.

If the application fails during a critical action, I would expect it to fail gracefully, preserve user data where possible, avoid duplicate operations, and clearly communicate the current state to the user.

When testing network instability, I would use controlled scenarios such as slow connections, high latency, temporary disconnections, and connection recovery. I would then verify both the user experience and the final state of the data.

My personal principle is:

**"Think beyond the happy path, test the boundaries, and make sure failures are safe and understandable."**
