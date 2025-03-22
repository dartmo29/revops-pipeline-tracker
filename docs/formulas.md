# Sales Pipeline Tracker - Formula Documentation

This document details all the key formulas used throughout the Sales Pipeline Tracker template.

## Deal Tracker Formulas

### Days in Stage Calculation
```
=IF(DateEnteredStage<>"", TODAY()-DateEnteredStage, "")
```
**Purpose:** Calculates how many days a deal has been in its current stage.
**Variables:**
- `DateEnteredStage`: The date when the deal entered its current stage
- `TODAY()`: Current date function

### Weighted Value Calculation
```
=IF(DealValue<>"", DealValue*VLOOKUP(CurrentStage, StageDefinitions, 2, FALSE)/100, "")
```
**Purpose:** Calculates the probability-weighted value of each deal.
**Variables:**
- `DealValue`: The full potential value of the deal
- `CurrentStage`: The deal's current sales stage
- `StageDefinitions`: Named range containing stage names and probability percentages
- The `/100` converts percentage to decimal

### Stage Duration Warning
```
=IF(DaysInStage > VLOOKUP(CurrentStage, StageExpectedDurations, 2, FALSE), "WARNING", "")
```
**Purpose:** Flags deals that have been in a stage longer than the expected duration.
**Variables:**
- `DaysInStage`: Calculated days in current stage
- `CurrentStage`: The deal's current sales stage
- `StageExpectedDurations`: Named range with expected durations for each stage

### Deal Priority Calculation
```
=IF(AND(WeightedValue>=HighPriorityThreshold, DaysInStage<=5), "High",
  IF(AND(WeightedValue>=MediumPriorityThreshold, DaysInStage<=10), "Medium", "Low"))
```
**Purpose:** Assigns a priority level based on deal value and age.
**Variables:**
- `WeightedValue`: The probability-adjusted deal value
- `DaysInStage`: How long the deal has been in its current stage
- `HighPriorityThreshold` and `MediumPriorityThreshold`: Configurable value thresholds

### Date Highlighting for Next Actions
```
=IF(NextActionDate<TODAY(), "Overdue",
  IF(NextActionDate=TODAY(), "Today",
    IF(AND(NextActionDate>TODAY(), NextActionDate<=TODAY()+7), "This Week", "")))
```
**Purpose:** Highlights the status of follow-up actions.
**Variables:**
- `NextActionDate`: The date when the next action is due
- `TODAY()`: Current date function

## Pipeline Dashboard Formulas

### Total Pipeline Value
```
=SUMIFS(DealValues, DealStages, "<>Closed Lost")
```
**Purpose:** Calculates the sum of all deal values that aren't closed lost.
**Variables:**
- `DealValues`: Range containing all deal values
- `DealStages`: Range containing all deal stages

### Total Weighted Pipeline Value
```
=SUMIFS(WeightedValues, DealStages, "<>Closed Lost")
```
**Purpose:** Calculates the sum of all probability-weighted deal values.
**Variables:**
- `WeightedValues`: Range containing all weighted deal values
- `DealStages`: Range containing all deal stages

### Average Deal Size
```
=IF(COUNTIFS(DealStages, "<>Closed Lost")>0, 
   SUMIFS(DealValues, DealStages, "<>Closed Lost")/COUNTIFS(DealStages, "<>Closed Lost"), 0)
```
**Purpose:** Calculates the average value of all open deals.
**Variables:**
- `DealValues`: Range containing all deal values
- `DealStages`: Range containing all deal stages

### Pipeline by Stage
```
=SUMIFS(DealValues, DealStages, StageName)
```
**Purpose:** Calculates the total deal value in each stage for visualization.
**Variables:**
- `DealValues`: Range containing all deal values
- `DealStages`: Range containing all deal stages
- `StageName`: Specific stage name to filter by

### Pipeline by Month
```
=SUMIFS(DealValues, ExpectedCloseDates, ">="&EOMONTH(TODAY(), MonthOffset), 
  ExpectedCloseDates, "<="&EOMONTH(TODAY(), MonthOffset+1)-1)
```
**Purpose:** Calculates the total deal value expected to close in each month.
**Variables:**
- `DealValues`: Range containing all deal values
- `ExpectedCloseDates`: Range containing expected close dates
- `MonthOffset`: Number of months from current month (0 for current, 1 for next, etc.)
- `EOMONTH()`: End of month date function

### At-Risk Deals Identification
```
=IF(AND(LastActivityDate<TODAY()-7, NextActionDate=""), TRUE, FALSE)
```
**Purpose:** Identifies deals with no recent activity and no scheduled next action.
**Variables:**
- `LastActivityDate`: Date of the most recent activity
- `NextActionDate`: Date of the next scheduled action

## Activity Log Formulas

### Upcoming Activities Count
```
=COUNTIFS(FollowUpDates, ">="&TODAY(), FollowUpDates, "<="&TODAY()+7)
```
**Purpose:** Counts the number of activities scheduled for the next 7 days.
**Variables:**
- `FollowUpDates`: Range containing all follow-up dates
- `TODAY()`: Current date function

### Overdue Activities Count
```
=COUNTIFS(FollowUpDates, "<"&TODAY(), ActivityCompleted, "FALSE")
```
**Purpose:** Counts the number of activities that are overdue and not completed.
**Variables:**
- `FollowUpDates`: Range containing all follow-up dates
- `ActivityCompleted`: Boolean indicating if the activity is completed
- `TODAY()`: Current date function

### Activities by Deal Aggregation
```
=COUNTIFS(ActivityDealNames, DealName)
```
**Purpose:** Counts the number of activities for each deal.
**Variables:**
- `ActivityDealNames`: Range containing deal names from the activity log
- `DealName`: Specific deal name to count activities for

## Reports Tab Formulas

### Stage Conversion Rate
```
=IFERROR(COUNTIFS(PreviousStages, PriorStageName, CurrentStages, CurrentStageName) / 
  COUNTIF(PreviousStages, PriorStageName), 0)
```
**Purpose:** Calculates the conversion rate from one stage to the next.
**Variables:**
- `PreviousStages`: Range containing previous stages for all deals
- `CurrentStages`: Range containing current stages for all deals
- `PriorStageName`: Name of the prior stage in the sequence
- `CurrentStageName`: Name of the current stage in the sequence

### Overall Lead-to-Close Rate
```
=IFERROR(COUNTIFS(DealStages, "Closed Won") / 
  (COUNTIFS(DealStages, "Closed Won") + COUNTIFS(DealStages, "Closed Lost")), 0)
```
**Purpose:** Calculates the overall win rate for closed deals.
**Variables:**
- `DealStages`: Range containing all deal stages

### Average Sales Cycle Length
```
=AVERAGEIFS(SalesCycleLengths, DealStages, "Closed Won")
```
**Purpose:** Calculates the average number of days from creation to close for won deals.
**Variables:**
- `SalesCycleLengths`: Range containing the duration from deal creation to close
- `DealStages`: Range containing all deal stages

### Team Performance - Close Rate by Rep
```
=IFERROR(COUNTIFS(DealOwners, RepName, DealStages, "Closed Won") / 
  COUNTIFS(DealOwners, RepName, DealStages, "<>Open"), 0)
```
**Purpose:** Calculates the close rate for each sales rep.
**Variables:**
- `DealOwners`: Range containing owner names for all deals
- `DealStages`: Range containing all deal stages
- `RepName`: Name of the specific sales rep

### Source Effectiveness - Average Deal Size by Source
```
=IFERROR(AVERAGEIFS(DealValues, LeadSources, SourceName), 0)
```
**Purpose:** Calculates the average deal size for each lead source.
**Variables:**
- `DealValues`: Range containing all deal values
- `LeadSources`: Range containing lead sources for all deals
- `SourceName`: Specific lead source name

## Forecast Integration Formulas

### Pipeline by Forecast Month
```
=SUMIFS(DealValues, ExpectedCloseDates, ">="&MonthStartDate, 
  ExpectedCloseDates, "<="&MonthEndDate, DealStages, "<>Closed Lost")
```
**Purpose:** Summarizes the pipeline value by month for forecast integration.
**Variables:**
- `DealValues`: Range containing all deal values
- `ExpectedCloseDates`: Range containing expected close dates
- `MonthStartDate`: First day of the month
- `MonthEndDate`: Last day of the month
- `DealStages`: Range containing all deal stages

### Weighted Pipeline by Forecast Month
```
=SUMIFS(WeightedValues, ExpectedCloseDates, ">="&MonthStartDate, 
  ExpectedCloseDates, "<="&MonthEndDate, DealStages, "<>Closed Lost")
```
**Purpose:** Summarizes the weighted pipeline value by month for forecast integration.
**Variables:**
- `WeightedValues`: Range containing all weighted deal values
- `ExpectedCloseDates`: Range containing expected close dates
- `MonthStartDate`: First day of the month
- `MonthEndDate`: Last day of the month
- `DealStages`: Range containing all deal stages

### Pipeline Coverage Ratio
```
=ForecastMonthWeightedPipeline / ForecastMonthTarget
```
**Purpose:** Calculates the ratio of weighted pipeline to target, indicating forecast confidence.
**Variables:**
- `ForecastMonthWeightedPipeline`: Weighted pipeline value for the forecast month
- `ForecastMonthTarget`: Revenue target for the forecast month

## Conditional Formatting Formulas

### Deal Age Warning
```
=AND(DaysInStage > StageExpectedDuration * 0.7, DaysInStage <= StageExpectedDuration)
```
**Purpose:** Applies yellow highlighting to deals approaching the expected stage duration.
**Variables:**
- `DaysInStage`: Calculated days in current stage
- `StageExpectedDuration`: Expected duration for the current stage

### Deal Age Critical
```
=DaysInStage > StageExpectedDuration
```
**Purpose:** Applies red highlighting to deals that have exceeded the expected stage duration.
**Variables:**
- `DaysInStage`: Calculated days in current stage
- `StageExpectedDuration`: Expected duration for the current stage

### Highlighting High Value Deals
```
=DealValue >= HighValueThreshold
```
**Purpose:** Applies special formatting to high-value deals.
**Variables:**
- `DealValue`: The full potential value of the deal
- `HighValueThreshold`: Configurable threshold for high-value deals

### Activity Status Highlighting
```
=NextActionDate < TODAY()
```
**Purpose:** Highlights overdue activities in red.
**Variables:**
- `NextActionDate`: The date when the next action is due
- `TODAY()`: Current date function