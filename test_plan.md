[Test Scope](index.md) | [Test Plan](test_plan.md) | [Test Procedure for Build](test_procedure.md) | [Validation Test](validation_test.md)

# Test Plan

The ENDA application is a complicated system empassing a number of separated subsystems, including:

1. The core engine module containing the business logics utilizing Apache Kafka or similar data streaming analytic engines to process data gathering from the users’ devices.

2. App for the wearable devices to collecting users’ biometrics data.

3. Lastly the web application interface for setting management, visualization and communication between three actors in the system.

For the test plan, our team proposes to use the bottom-up integration testing strategy, in which the lower level modules are tested first. These tested modules are then further used to facilitate the testing of higher level modules. The process continues until all modules at top level are tested. Once the lower level modules are tested and integrated, then the next level of modules are formed. The advantages of the proposed bottom-up integration testing strategy are: 1) It’s easier to locate the defects among the data flows in the lower level modules before the testing task becomes too complicated to manage. 2) Unlike the Big Bang testing strategy, there is no need to wait for all modules to be developed to begin the testing. Once some connected lower level modules are developed and ready to go, the testing task can begin while other higher level modules are developed.

Given the characteristics and architectural design of the ENDA application, our team proposes to conduct 4-phase integration testing for the target system. The diagram of the testing plan is showing as below:

![Test_Plan_Diagram](https://user-images.githubusercontent.com/24898162/100957230-14be3980-34e8-11eb-8178-c0239afa87f0.png)

## The First Phase

The first phase of the test plan is to conduct integration testing on the subsystem level. For example, for the web application subsystem, the mock data, stubs and drivers will be utilized to imitate the RESTful API endpoint responses to test if the subsystem as a whole exhibits the expected results outlined from the requirements documents and acceptance criteria. Also the test will cover the workflow from module to module to discover any unwanted or incorrect user interface behaviors. This phase is very crucial, since it is the first tier of integration testing. All the lower level modules had already passed individual unit testing, however when combined together, they may create a number of defects which need to be addressed and fixed.

## The Second Phase

The second phase of the test plan is to conduct the testing for the integration between the core engine module and the wearable app subsystems. These two subsystems are where the core business logics reside and represent the data tier. In the first phase each subsystem already passed the mock data integration test, and this phase will test these two subsystems integrated together with the QA account and database. Because of the consumption of the real data gathered from the wearable devices, this phase of integration testing will catch any unexpected error and defect caused by the mock data environment.

## The Third Phase

The third phase of the test plan is to conduct the integration testing of the data tier and the application tier. In the second phase, data tier subsystems have already been tested with real data in the QA environment. In this phase, the main focus is on the application tier’s reception of the real data. The data tier will connect with the application tier and supply real data in the QA environment, therefore this phase of integration testing will catch any unexpected defects caused by the mock data environment previously used in the first phase for the web application subsystem.

## The Final Phase

The final phase of the test plan is to conduct the integration testing of the ENDA system as a whole in the PROD environment. Given previously the data tier and the application tier subsystems already passed all the test cases in the QA environment which is very similar to the PROD environment, the errors and defects should be very minimal in this phase. The main focus of this integration testing phase should be catching any edge cases or anomalies caused by the network or cloud services.
