# HealthConnect_Clinic_Week7

## Testing, Refinement & End-to-End Validation

## Project Overview

The HealthConnect Clinic Experience Lab focuses on the question:

> **How can HealthConnect Clinic use data and AI to reduce missed appointments and improve the patient support experience?**

Week 7 continued directly from the analysis, dashboard development and validation completed in Week 6.

The focus was **not to start a new analysis**, but to systematically test the existing analytical outputs, identify weaknesses, refine the dashboard where necessary, retest the changes, and validate the Data Analytics contribution within the wider HealthConnect solution.

The Week 7 workflow followed:

**Test → Finding → Action → Retest → Validated Result**

## Week 7 Objectives

The main objectives were to:

- Validate the core Week 6 KPIs.
  
- Retest important Week 6 analytical findings.

- Check analytical calculations against the cleaned dataset.

- Test Power BI visuals, calculations and slicers.

- Refine the existing Week 6 dashboard.

- Validate important findings across relevant variable combinations.

- Complete meaningful cross-track testing with Data Science.

- Document limitations, remaining issues and recommendations for Week 8.

## Dataset

The analysis used the cleaned HealthConnect appointment dataset developed during Week 5.

- **Rows:** 5,000
  
- **Columns:** 18

## Week 7 Testing

### 1. KPI Validation

The following Week 6 KPIs were independently recalculated and validated:

| KPI | Week 7 Result |
|---|---:|
| Total Appointments | 5,000 |
| No-Show Rate | Validated against Week 6 |
| Attendance Rate | Validated against Week 6 |
| Reminder Coverage | 72.68% |
| Average Booking Lead Time | 29.64 days |

The KPI calculations remained reproducible using the cleaned dataset.

### 2. Analytical Validation

Selected Week 6 findings were retested rather than treated as new analyses.

The following relationships were validated:

- Lead Time × Previous No-Show History
  
- Lead Time × Reminder Status

- Previous No-Show History × Reminder Status

- Waiting Time × Appointment Outcome

- Distance × Appointment Outcome

- Age Group × Appointment Outcome

## Key Validation Findings

### Lead Time × Previous No-Show History

The combined analysis continued to show higher observed no-show rates among patients with longer booking lead times and greater previous no-show history.

For the **46–60 day** lead-time group:

| Previous No-Shows | No-Show Rate |
|---|---:|
| 0 | 61.68% |
| 1 | 73.67% |
| 2+ | 82.11% |

The Week 6 finding was reproduced during Week 7.

### Lead Time × Reminder Status

The Week 6 relationship between booking lead time and reminder status was also reproduced.

For appointments without reminders, the observed no-show rate increased from approximately **29.94%** in the shortest lead-time group to **73.51%** in the 46–60 day group.

For appointments with reminders, the rate increased from approximately **27.06%** to **65.66%** across the same lead-time range.

The highest observed combination remained:

**46–60 days + No Reminder = 73.51%**

across **302 appointments**.

Reminder status was treated as an operational variable rather than evidence of causation.

### Previous No-Show History × Reminder Status

The Week 7 retest reproduced the Week 6 pattern:

| Previous No-Shows | No Reminder | Reminder |
|---|---:|---:|
| 0 | 45.44% | 42.80% |
| 1 | 56.54% | 52.32% |
| 2+ | 68.24% | 58.22% |

The highest observed combination was **2+ previous no-shows with no reminder**, at **68.24%**, across **148 appointments**.

### Waiting Time × Appointment Outcome

Waiting time remained a relatively weak signal.

Average waiting time was approximately:

- **Attended:** 24.29

- **No-Show:** 24.20

The 60+ waiting-time group showed a higher no-show rate, but contained only **3 appointments**, so this result was interpreted cautiously.

### Distance × Appointment Outcome

The Week 6 distance finding remained consistent after retesting.

- **0–5 distance group:** 46.45% no-show rate

- **20+ distance group:** 57.76% no-show rate

This represents an observed association rather than evidence that distance directly causes missed appointments.

### Age Group × Appointment Outcome

The Week 6 age-group findings were also reproduced.

Examples:

- **55–64:** 50.75% no-show rate across 800 appointments
  
- **65+:** 45.12% no-show rate across 1,241 appointments

These differences were treated as descriptive patterns rather than causal relationships.

## Dashboard Testing & Refinement

The existing Week 6 Power BI dashboard was **refined rather than replaced**.

### Refinements

The Week 7 dashboard updates included:

- Incorporating the validated combined-variable findings.
  
- Adding **No-Show Rate by Distance Group**.

- Adding a **Distance Group** slicer.

- Retaining the existing **Appointment Type** slicer.

- Retaining the existing **Age Group** slicer.

- Maintaining slicer synchronisation across the relevant pages.

### Dashboard Testing

The refined dashboard was checked for:

- KPI consistency.
  
- Visual calculation accuracy.

- Consistency with Python validation.

- Correct slicer behaviour.

- Correct filtering of visual outputs.

- Representation of the validated analytical findings.

The refined dashboard passed the Week 7 testing requirements.

## Cross-Track Testing — Data Science

Week 7 included a meaningful cross-track testing activity with the **Data Science** track.

The purpose was to determine whether important Data Analytics findings were consistent with the variables and patterns identified through predictive modelling.

### Lead Time

Data Analytics identified longer booking lead time as an important pattern in observed no-show behaviour.

Data Science also identified the **41–60 day lead-time band** as an important model feature.

### Previous No-Show History

Data Analytics showed increasing observed no-show rates among patients with greater previous no-show history.

Data Science similarly identified variables such as:

- `prev_no_show_rate`

- `high_prev_no_show`

as important model features.

### Reminder Variables

Reminder-related variables were relevant to both tracks.

However, the available observational data does not establish that reminders directly cause differences in attendance.

The reminder findings were therefore retained as an **operational consideration**, rather than a causal conclusion.

### Cross-Track Outcome

The collaboration provided consistency between the descriptive Data Analytics findings and relevant Data Science modelling outputs.

The shared findings around **lead time** and **previous no-show history** were retained for wider HealthConnect integration.

## Validated Business Insights

Following Week 7 testing, the following findings were retained:

1. **Longer booking lead time is associated with higher observed no-show rates.**
2. **Previous no-show history is associated with higher observed no-show rates.**
3. **Long booking lead time combined with previous no-show history shows a stronger observed pattern of missed appointments.**
4. **Reminder-related differences are observable but should not be interpreted as causal evidence.**
5. **Greater distance is associated with higher observed no-show rates in the available dataset.**
6. **Waiting time shows a weak relationship with appointment outcome.**
7. **Age-group differences are observable but should be interpreted descriptively.**

## Week 7 Improvements

The main improvements made during Week 7 were:

- Independent validation of Week 6 KPIs.
  
- Retesting of selected Week 6 analytical findings.

- Validation of combined-variable analyses.

- Refinement of the existing Power BI dashboard.

- Addition of distance-based visualisation.

- Addition of a Distance Group slicer.

- Testing of dashboard filters and interactions.

- Cross-track validation with Data Science.

- Clearer distinction between observed association and causation.

## Testing Outcome

The Week 7 testing established that the major Week 6 analytical outputs were reproducible using the cleaned dataset.

No major analytical error requiring the Week 6 findings to be discarded or fundamentally changed was identified.

The existing dashboard was successfully refined and retested, while the cross-track testing provided additional support for carrying important findings into the wider HealthConnect solution.

## Final Outcome

Week 7 successfully transitioned the HealthConnect Data Analytics work from **analysis and development into systematic testing, refinement and end-to-end validation**.

The key Week 6 KPIs and analytical findings were retested and remained reproducible. The existing Power BI dashboard was refined based on the validated findings, and the Data Analytics outputs were meaningfully tested against the Data Science work.

The validated evidence provides a stronger foundation for the **Week 8 Final Integration and Presentation** stage.
