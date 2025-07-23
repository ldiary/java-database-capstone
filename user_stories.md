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
 When I log out ot the Admin portal
 Then my log out attempt should be successful
 ```
3. **Can add doctors to the portal**
```gherkin
 Given I am an Admin
 And I am successfully logged in the Admin portal
 When I add a doctor in the portal
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
 When run MySQL CLI procedure for retrieving appointments per month
 Then I can retrieve the number of appointments per month
 ```

**Priority:** High

**Story Points:** 8 points

**Notes:**
- Triggering of MySQL CLI procedure should be available in the Admin portal
