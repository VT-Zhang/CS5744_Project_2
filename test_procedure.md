[Test Scope](index.md) | [Test Plan](test_plan.md) | [Test Procedure for Build](test_procedure.md) | [Validation Test](validation_test.md)

# Test Procedure for Build

The test procedure will follow the outline set by the test plan and is broken up into four phases. The first phase focuses on subsystem integration. The second phase tests integration between the core engine module and the wearable app subsystems. The third phase handles integration testing of the data tier and the application tier. The fourth and final phase features integration testing for the EDNA system in the PROD environment. Each phase will be described by their associated test procedures below.

## Phase One

The first phase of the test plan will begin the bottom-up testing strategy by conducting integration testing among all of the lowest level subsystems of the three mid-layer modules. In the Web App subsystems, tests will check the functionality of the login, user interface, notification module, communication module, and the security module. The test will confirm that users will be able to utilize the functionalities of the login and interface and that the notification, communication, and security modules behave as expected. Performance must be tested particularly within the Core Engine and Wearable App modules as they bear the most processing overhead for the system. To test, we will need mock data, stubs, and drivers to replicate real world results. One test case skeleton features a heavy use with multiple notifications in quick succession to test the processing speed. Another test case will test both the security and login modules by performing edge case and malicious input validation to prevent malicious activity on the system and ensure good traffic performs well. One other test case skeleton focuses on a new user setup process including the wearable app and new account setup and linking the account to their device. With these and other test cases, we can ensure the integration testing at the next tier up is built on a solid, well-integrated foundation.

## Phase Two

The second phase tests the integration of the Wearable App and Core Engine modules. The tests in this phase ensure seamless integration into the next tier, the Data Tier. The tests build on those from Phase 1 due to the bottom up testing strategy. To accomplish integration testing in this phase, we will focus on the functionality, performance, and design of the Core Engine and Wearable App modules and their interaction with the Phase 1 build. A test case skeleton for this phase would take the mock data from both the Wearable App and Core Engine to check for compatibility and compilation issues. Mock data is the key external component to complete this phase.

## Phase Three

The third phase of integration testing focuses on the next tier up in bottom-up fashion, the Data Tier and the Application Tier. In this phase of testing we will assess the Data Tier’s reception, integration, and distribution of the mock data as tested in Phase 2. The Application Tier integration testing will assess the functionality of the top-level application module in aggregating the data and integrating with the Data Tier. A test skeleton for Phase 3 is a full integration testing phase, so mock data will be supplied to the Data Tier modules and testing will check whether there are any errors on the application side in modules such as security, communication, and notification. Another test case skeleton is similar to that used in Phase 1 as providing an influx of inputs in quick succession to check the impacts across the Application Tier. Mock data is again key to this phase.

## Phase Four

The final phase tests the full EDNA integration as one system. The testing focus at this stage is on edge cases and errors produced in the PROD environment. To replicate PROD errors, a test case skeleton would simulate network and cloud services to ensure seamless integration at the top level of the hierarchy. Mock data will be used extensively to ensure there are no issues between the data and application tiers and that users are fully integrated.
