# Jira Rovo AI Output – UC10 Create Job Overview

Based on the documentation provided for **UC10: Create Job**, here are the requirements formatted for QA review.

## 1. User Story

**As a** Recruiter or Manager,  
**I want to** trigger the job creation process from the Job List screen,  
**So that** I can access the Create Job screen and begin adding new positions to the system.

## 2. Acceptance Criteria

- **AC 1:** Verify that the "Add" icon is visible and clickable for both Recruiters and Managers when they are on the Job List screen.
- **AC 2:** Verify that clicking the "Add" icon located above the grid-view table successfully triggers the navigation flow.
- **AC 3:** Verify that the system redirects the user from the Job List screen to the **Create Job** screen upon clicking the trigger.
- **AC 4:** Verify that the post-condition is met and the Create Job screen is displayed as expected.

## 3. High-Level Test Scenarios

| Scenario ID | Test Scenario Description | Expected Result |
|---|---|---|
| TS_01 | Verify access to Job Creation trigger as a **Recruiter**. | The Add icon is displayed and functional on the Job List screen. |
| TS_02 | Verify access to Job Creation trigger as a **Manager**. | The Add icon is displayed and functional on the Job List screen. |
| TS_03 | Verify navigation flow from Job List to Create Job screen. | Clicking the Add icon successfully loads the Create Job screen. |
| TS_04 | Verify UI placement of the trigger. | The Add icon is located specifically above the grid-view table. |

## 4. Constraints & Rules Applied

- **Scope:** Limited strictly to the transition between the Job List and Create Job screen.
- **Exclusions:** No field-level validation (Title, Skills, Salary, etc.) or post-submission logic (Save/Cancel/Status) has been included per the specific instructions.
