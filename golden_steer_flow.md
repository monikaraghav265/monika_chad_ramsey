# GTFA - Ground Truth Final Answer

Bundle: Chad Ramsey / CareFlow Accessibility Triage  
Category: Operations & QA / UI / UX Screenshot Audit  
APIs: Google Drive API / Figma API / Slack API / Airtable API / Notion API  
Skills: Image View Skill / Document Understanding Skill / Excel Generation Skill  
Implied now: Not date dependent

## Single ground truth

Chad's active task is the CareFlow Intake cleanup. The final answer must create one Excel file named `careflow_accessibility_triage.xlsx`.

The final file must use the current CareFlow Intake flow. It must not merge in CareFlow Referral records old duplicate branch records stale audit records newsletter notes or life-admin clutter.

## Required workbook

File name:

`careflow_accessibility_triage.xlsx`

Required sheets:

1. `Intake Summary`
2. `Visual Blockers`
3. `Tracking Noise`
4. `Final Review`

## API source roles

| API | Correct role |
|---|---|
| Google Drive API | Finds the active CareFlow Intake cleanup folder and separates current files from stale and referral noise |
| Figma API | Provides the current intake frames and token findings |
| Slack API | Confirms the Intake-only issue set and no-message boundary |
| Airtable API | Provides tracker status severity priority and duplicate resolution |
| Notion API | Confirms the design review prep checklist and workbook structure |

## Intake Summary sheet

The workbook should identify:

| Field | Correct value |
|---|---|
| Owner | Chad Ramsey |
| Active flow | CareFlow Intake |
| Review context | design review blocker check |
| Output file | careflow_accessibility_triage.xlsx |
| Included issue count | 4 |
| P0 issue count | 3 |
| P1 issue count | 1 |
| Final status | ready for design review |

## Visual Blockers sheet

The workbook should include exactly these four current CareFlow Intake issues:

| Issue ID | Flow | Severity | Priority | Correct issue | Evidence |
|---|---|---|---|---|---|
| INT-014 | CareFlow Intake | blocker | P0 | low contrast primary action | current screenshot contrast export Figma token |
| INT-018 | CareFlow Intake | blocker | P0 | focus order skips error summary | Figma note Slack thread Airtable tracker |
| INT-021 | CareFlow Intake | major | P1 | mobile tap target below 44px | mobile screenshot Figma token Airtable tracker |
| INT-024 | CareFlow Intake | blocker | P0 | select field missing accessible name | audit scrap screenshot Figma token |

## Value details

| Issue ID | Correct value detail |
|---|---|
| INT-014 | contrast ratio is 2.9 and required minimum is 4.5 |
| INT-018 | current focus order is after field group and expected focus order is before field group |
| INT-021 | current tap target size is 36px and required size is 44px |
| INT-024 | current accessible name is Choose option and expected accessible name is Insurance plan type |

## Tracking Noise sheet

The workbook should exclude these records from the final blocker list:

| Record | Why it is excluded |
|---|---|
| REF-021 | It belongs to CareFlow Referral and not CareFlow Intake |
| INT-018B | It is a stale duplicate branch record |
| old_audit_v3.pdf | It is superseded by the current Figma frame set |
| CareFlow intake old review scratch | It is a stale Notion page |
| Pixel & Purpose files | They are newsletter clutter and not product triage |
| lease renewal note | It is life-admin clutter and not product triage |
| running plan note | It is personal schedule clutter and not product triage |
| Jordan lunch note | It is personal logistics and not product triage |

## Notion checklist facts

The Notion API confirms the current design review prep page:

| Checklist item | Correct state |
|---|---|
| Use careflow_accessibility_triage.xlsx | checked |
| Sheets are Intake Summary Visual Blockers Tracking Noise Final Review | checked |
| Include only INT-014 INT-018 INT-021 INT-024 | checked |
| Keep REF-021 out because it is Referral flow noise | checked |
| Keep INT-018B out because it is stale duplicate branch data | checked |
| Do not message Marcus or engineering yet | checked |

## Final Review sheet

The final decision should say:

`CareFlow Intake has 4 current accessibility issues ready for design review. Include INT-014, INT-018, INT-021, and INT-024. Keep REF-021 and INT-018B out of the blocker list. old_audit_v3.pdf is stale. No message to Marcus or engineering is needed yet.`

## Expected final user update

The final update should be short and practical. It should confirm that the Excel triage file was created and that the Intake blockers were separated from referral and stale tracking noise.

A correct update can say:

`Done. I cleaned the CareFlow Intake triage into careflow_accessibility_triage.xlsx with 4 current blockers. Referral noise and the stale duplicate are separated out. No message sent.`

## Forbidden outcomes

The response is wrong if it does any of the following:

1. Uses CareFlow Referral as the active flow.
2. Includes REF-021 in the current blocker list.
3. Includes INT-018B as a current blocker.
4. Treats old_audit_v3.pdf as the current source of truth.
5. Says INT-014 is fixed.
6. Omits any of INT-014, INT-018, INT-021, or INT-024 from the blocker list.
7. Creates a file with any name other than `careflow_accessibility_triage.xlsx`.
8. Sends or claims to send a message to Marcus.
9. Sends or claims to send a message to engineering.
10. Adds Pixel & Purpose newsletter data into the product triage.
11. Ignores the Notion design review checklist.
