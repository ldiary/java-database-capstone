# User Stories

## Admin User Stories

**Title:**
_As an Admin, I want a secure Admin portal, so that I can manage the platform securely._

**Acceptance Criteria:**
1. **Can log into the portal with username and password**
 ```gherkin
 Given I am an Admin
 When I log into the Admin portal using my username and password
 Then my login attempt should be successful
 ```
2. **Can log out of the portal**
```gherkin
 Given I am an Admin
 And I am successfully logged in the Admin portal
 When I log out of the Admin portal
 Then my log out attempt should be successful
 ```
3. **Can add doctors to the portal**
```gherkin
 Given I am an Admin
 And I am successfully logged in the Admin portal
 When I add a doctor into the system
 Then the doctor's profile should be added successfully
 ```
4. **Can delete doctor**
```gherkin
 Given I am an Admin
 And I am successfully logged in the Admin portal
 And a doctor is present in the system
 When I delete the doctor's profile
 Then the doctor is deleted from the system
 ```
5. **Can get number of appointments per month**
```gherkin
 Given I am an Admin
 And I am successfully logged in the Admin portal
 When I run MySQL CLI procedure for retrieving appointments per month
 Then I can retrieve the number of appointments per month
 ```

**Priority:** High

**Story Points:** 8 points

**Notes:**
- Triggering of MySQL CLI procedure should be available in the Admin portal

## Patient User Stories
**Title:**
_As a Patient, I want a Patient portal, so that I can find doctors and securely manage my appointment._

**Acceptance Criteria:**
1. Can view list of doctors without logging in
 ```gherkin
 Given I am a Patient
 And I am not logged into the Patient portal
 When I select a doctors' list
 Then I should be able to see a list of doctors
 ```
2. Can sign up using email and password
 ```gherkin
 Given I am a Patient
 And I am not logged into the Patient portal
 When I select sign up
 And I enter my email and password
 Then I should be successfully registered into the system
 ```
3. Can log into the portal to manage bookings
 ```gherkin
 Given I am a Patient
 And I am not logged into the Patient portal
 When I log into the portal using my email and password
 Then my login attempt should be successful
 ```
4. Can log out of the portal
```gherkin
 Given I am a Patient
 And I am successfully logged in the Patient portal
 When I log out of the Patient portal
 Then my log out attempt should be successful
 ```
5. Can view upcoming appointments
```gherkin
 Given I am a Patient
 And I am successfully logged in the Patient portal
 When I select my upcoming appointments
 Then I should see the list of my upcoming appointments
 ```

**Priority:** High

**Story Points:** 8 points

**Notes:**
- Make sure to test the view of appointments when there are 1) zero appointment and 2) one or more appointments