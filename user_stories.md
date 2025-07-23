# User Stories

## Admin User Stories

**Title:**
_As an Admin, I want a secure Admin Portal, so that I can manage the platform securely._

**Acceptance Criteria:**
1. **Can log into the portal with username and password**
 ```gherkin
 Given I am an Admin
 When I log into the Admin Portal using my username and password
 Then my login attempt should be successful
 ```
2. **Can log out of the portal**
```gherkin
 Given I am an Admin
 And I am successfully logged in the Admin Portal
 When I log out of the Admin Portal
 Then my log out attempt should be successful
 ```
3. **Can add doctors to the portal**
```gherkin
 Given I am an Admin
 And I am successfully logged in the Admin Portal
 When I add a doctor into the system
 Then the doctor's profile should be added successfully
 And the doctor can successfully log into Doctor Portal
 ```
4. **Can delete doctor**
```gherkin
 Given I am an Admin
 And I am successfully logged in the Admin Portal
 And a doctor is present in the system
 When I delete the doctor's profile
 Then the doctor is deleted from the system
 And the doctor can no longer log into the Doctor Portal
 ```
5. **Can get number of appointments per month**
```gherkin
 Given I am an Admin
 And I am successfully logged in the Admin Portal
 When I run MySQL CLI procedure for retrieving appointments per month
 Then I can retrieve the number of appointments per month
 ```

**Priority:** _High_

**Story Points:** _8 points_

**Notes:**
- _Criteria 3 and 4 will need Doctor's profile to verify changes are reflected in Doctor Portal._
- _Triggering of MySQL CLI procedure should be available in the Admin Portal_

## Patient User Stories
**Title:**
_As a Patient, I want a Patient portal, so that I can find doctors and securely manage my appointment._

**Acceptance Criteria:**
1. **Can view list of doctors without logging in**
 ```gherkin
 Given I am a Patient
 And I am not logged into the Patient Portal
 When I select a doctors' list
 Then I should be able to see a list of doctors
 ```
2. **Can sign up using email and password**
 ```gherkin
 Given I am a Patient
 And I am not logged into the Patient Portal
 When I select sign up
 And I enter my email and password
 Then I should be successfully registered into the system
 ```
3. **Can log into the portal to manage bookings**
 ```gherkin
 Given I am a Patient
 And I am not logged into the Patient Portal
 When I log into the portal using my email and password
 Then my login attempt should be successful
 ```
4. **Can log out of the portal**
```gherkin
 Given I am a Patient
 And I am successfully logged in the Patient Portal
 When I log out of the Patient Portal
 Then my log out attempt should be successful
 ```
5. **Can view upcoming appointments**
```gherkin
 Given I am a Patient
 And I am successfully logged in the Patient Portal
 When I select my upcoming appointments
 Then I should see the list of my upcoming appointments
 ```

**Priority:** _High_

**Story Points:** _8 points_

**Notes:**
- _Make sure to test the view of appointments when there are 1) zero appointment and 2) one or more appointments_

## Doctor User Stories
**Title:**
_As a Doctor, I want a Doctor Portal, so that I can manage my availability and appointments securely._

**Acceptance Criteria:**
1. **Can log into the portal to manage appointments**
 ```gherkin
 Given I am a Doctor
 When I log into the Doctor Portal using my email and password
 Then my login attempt should be successful
 ```
2. **Can log out of the portal to protect data**
```gherkin
 Given I am a Doctor
 And I am successfully logged in the Doctor Portal
 When I log out of the Doctor Portal
 Then my log out attempt should be successful
 ```
3. **Can view appointment calendar to stay organized**
```gherkin
 Given I am a Doctor
 And I am successfully logged in the Doctor Portal
 When I select the calendar
 Then I should see my appointment calendar
 ```
4. **Can mark unavailability to inform patients only the available slots**
```gherkin
 Given I am a Doctor
 And I am successfully logged in the Doctor Portal
 And I am in the appointment calendar
 When I mark my unavailability in the calendar
 Then the appointment calendar should show I am not available
 And patient should see I am not available in the Doctor's list
 And patient should not be able to book an appointment with me when I am not available
 ```
5. **Can view patient details for upcoming appointment preparations**
```gherkin
 Given I am a Doctor
 And I am successfully logged in the Doctor Portal
 And I have an appointment coming
 When I select the appointment
 Then then I should see the patient details for that appointment
 ```
**Priority:** _High_

**Story Points:** _8 points_

**Notes:**
- _Criteria 5 will need a Doctor login profile to mark unavailability in the calendar and a Patient profile to confirm the change in Patient Portal._