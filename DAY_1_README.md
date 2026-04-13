# Daily_Tasks_Linkific   
DAY-1 Software Testing Fundamentals & Environment Setup 

1.Setup Testing Environment 
To prepare the required tools and environment for software testing activities.

  Browsers : Chrome, Firefox, Edge 
            Status : In built.
  Note-Taking Tool : One Note. 
  Screen recording Tool: Share X  (Andrid)
  Screenshot Tool : Snipping Tool( windows) 
 Git and github setup : Git installed 
                                    Github Account created 
                                    Github profile link: shared into dashboard.

2. SDLC and STLC comparison document.

SDLC – software development life cycle is a process used by the software industry to design, develop the quality softwares.
 
Phases are
1.Requirement analysis: define and document the product requirement      and get them approved from the customer or client.
Document- SRS software requirement specification.

2. Design : Based on the requirement specified in SRS, most of the design approach for the product architecture is proposed abd documented in a 
DDS - Design document specification.

3.Develop or Building phase: The programming code is generated as per FRDs during this stage.
there is no widely recognized or standardized acronym "FRIENDs" document used in the development phase.

4.Testing – this stage refers to the testing only stage of the product , where product defect are reported, tracked, foxed and retested, until the product reaches the quality standard defined in the SRS,

5.Deployment. Once the product is tested and ready to be deployed it is released formally in the appropriate market.


STLC– software testing life cycle is a sequence of different activities prerformed during the software testing process

These are the features as a tester need to notice and test 
Phases are 
Requirement Analysis–


Read the requirement and basically prepare alive set of requirement that tester point of view .

Planning– conyains an document , write what type of testing going to do , integration , system, UAT testing, how many day it takes , how many tester need , what type pr functional or non functional testing going to do.
Check on SDET.live/testplan.

Test case design 
Test execution
Defect reporting
Test closure 


3. Testing types classification document.
Functional testing:  verifies that each feature of the software application operates as expected with the requirement specifications. It focuses on the outputs based on specific inputs 
Ex : Checking if a "Login" button successfully takes you to the dashboard.

Non-functional testing:  verifies the behavioral aspects and quality and focuses on performance, scalability, security, and usability.
Ex: Checking if the app can handle 1,000 users at once without crashing (Performance) or if the text is easy to read (Usability).
Maintenance testing: This happens after a system is already deployed and is triggered by modifications, migrations, or retirement.
Regression testing :  It often involves running a large suite of test cases covering many different features.
Sanity testing: Narrow and deep. It focuses only on the specific component that was changed.

Change- Related Testing : These types are used specifically when code has been modified.
Re-testing (Confirmation Testing) :  restesting is testing the fixed bug and going through the test steps , still expected and actual results are same.
Regression : After the bug fixes or new feature added , checking the functionality works as before with out any breakage in it.

4. 7 principles examples: 
1. Testing shows the presence of defects : Testing can find bugs, but it cannot prove that there are no bugs left. It reduces the probability of undiscovered defects.
Ex: You run 1,000 tests on a login page and they all pass. This means the login works for those 1,000 cases, but it doesn't guarantee a bug won't appear on the 1,001st try with a different browser.
2. Exhaustive testing is impossible :Testing every single combination of inputs and preconditions is mathematically impossible for anything but the simplest programs.
Ex: A simple Age field that accepts numbers from 1 to 100. If you try to test every combination of valid numbers, invalid characters, and empty spaces across every possible device, you’d never finish. We use risk analysis to prioritize instead.
3. Early testing: Testing should start as soon as possible in the Software Development Life Cycle (SDLC) to catch defects when they are cheapest to fix.
Ex: If a tester reviews the requirements for a new feature and notices a contradiction, they can fix it in the document. If they wait until the code is written to find that error, it costs much more in developer time.
4. Defect clustering: In many systems, a small number of modules contain the majority of the bugs. This follows the Pareto Principle (the 80/20 rule).
Ex: In an e-commerce app, you might find that 80% of the crashes happen specifically in the "Payment Gateway" module, while the "Product Search" module is very stable.
5. Pesticide paradox: If you keep running the same set of tests, eventually those tests will no longer find new bugs. Testers must constantly review and update their test cases.
Ex:If you only test the "Add to Cart" button with one specific product, you might miss a bug that only happens when adding two different products at once.
6. Testing is context dependent : The way you test a video game is completely different from how you test a banking application or an autopilot system for a car.
Ex: A mobile game might prioritize "Usability" and "Fun," whereas a banking app prioritizes "Security" and "Data Integrity."
7. Absence-of-errors fallacy: A system with zero bugs is still a failure if it doesn't meet the users' needs or expectations.
Ex:You build a perfect, bug-free calculator app, but the buttons are so small that no one can tap them correctly. Even though there are no "defects," the product is a failure.

5.Testing glossary created
      A Testing Glossary is a centralized collection of specialized terms and definitions used in software testing. In the professional world, using the correct terminology is vital because it ensures that developers, testers, and stakeholders are all talking about the same thing.

Here are some terminology: 
Bug/Defect: Issue in software causing incorrect behavior
Error: Mistake made by developer
Failure: When software does not work as expected
Test Case: Step-by-step procedure to test a feature
Test Scenario: High-level test condition
Test Plan: Document describing testing scope and strategy
Requirement: Client/business need
Functional Testing: Testing application features
Non-Functional Testing: Testing performance/security/usability
Regression Testing: Ensure old features work after changes
Re-testing: Verify fixed defect works properly
Sanity Testing: Quick testing after minor change
Smoke Testing: Basic build verification testing
UAT: User Acceptance Testing
Unit Testing: Testing individual module
Integration Testing: Testing combined modules
System Testing: Testing complete application
Acceptance Testing: Testing from user perspective
Severity: Impact of defect
Priority: Urgency to fix defect

 


Testing levels: levels of testing are 
Unit testing ( component testing)-- test individual components or small unit 
Integration testing( combined components– test the integrated part, basically interationg the smaller units and testing. Ex: combining login , registration page and add to cart integrating these part and checking the functionality of them; 
System testing( complete system)--test the entrie system. Testing functional and non functional testing.
Acceptance testing ( user perspective )


 





