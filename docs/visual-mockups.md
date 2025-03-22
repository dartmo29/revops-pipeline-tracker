# Sales Pipeline Tracker - Visual Mockups

This document provides visual mockups of the template structure and layout.

## Tab 1: Instructions

```
+--------------------------------------------------+
| SALES PIPELINE TRACKER - INSTRUCTIONS            |
+--------------------------------------------------+
| Welcome to your Sales Pipeline Tracker!          |
|                                                  |
| This tool will help you track and manage your    |
| entire sales pipeline in one place.              |
|                                                  |
| SETUP STEPS:                                     |
| 1. Go to the Configuration tab                   |
| 2. Enter your business information               |
| 3. Customize your sales stages                   |
| 4. Add your team members                         |
| 5. Begin tracking deals in the Deal Tracker      |
|                                                  |
| [Quick Nav Links]                                |
| → Configuration                                  |
| → Pipeline Dashboard                             |
| → Deal Tracker                                   |
| → Activity Log                                   |
| → Reports                                        |
| → Forecast Integration                           |
+--------------------------------------------------+
```

## Tab 2: Configuration

```
+--------------------------------------------------+
| SALES PIPELINE TRACKER - CONFIGURATION           |
+--------------------------------------------------+
| BUSINESS INFORMATION         | VALUE             |
+------------------------------+-------------------+
| Business Name                | [Input field]     |
| Industry                     | [Dropdown]        |
| Business Model               | [Dropdown]        |
| Currency                     | [Dropdown]        |
+------------------------------+-------------------+
|                                                  |
| SALES STAGES                 | PROBABILITY       |
+------------------------------+-------------------+
| Initial Contact              | 10%               |
| Qualified                    | 25%               |
| Meeting Scheduled            | 40%               |
| Proposal Sent                | 60%               |
| Negotiation                  | 80%               |
| Closed Won                   | 100%              |
| Closed Lost                  | 0%                |
+------------------------------+-------------------+
|                                                  |
| DEAL CATEGORIES              | VALUE RANGE       |
+------------------------------+-------------------+
| Small                        | $0 - $5,000       |
| Medium                       | $5,001 - $15,000  |
| Large                        | $15,001+          |
+------------------------------+-------------------+
|                                                  |
| TEAM MEMBERS                 | ROLE              |
+------------------------------+-------------------+
| [Name 1]                     | [Role]            |
| [Name 2]                     | [Role]            |
| [Name 3]                     | [Role]            |
+------------------------------+-------------------+
```

## Tab 3: Pipeline Dashboard

```
+------------------------------------------------------------------+
|                   PIPELINE DASHBOARD                              |
+------------------------------------------------------------------+
|                                                                  |
| SUMMARY METRICS                                                  |
| +--------------+--------------+--------------+--------------+    |
| | Total Deals  | Pipeline Val | Weighted Val | Avg Deal Size|    |
| | 24           | $145,500     | $62,650      | $6,063       |    |
| +--------------+--------------+--------------+--------------+    |
|                                                                  |
+------------------------------------------------------------------+
|                             |                                    |
| PIPELINE BY STAGE           | DEALS BY CLOSE MONTH               |
| [Funnel Chart showing:      | [Bar Chart showing:                |
|  - # deals per stage        |  - Expected deals by month         |
|  - Value per stage          |  - Weighted value by month]        |
|  - % of total pipeline]     |                                    |
|                             |                                    |
+-----------------------------+------------------------------------+
|                                                                  |
| RECENT DEALS                                                     |
| +----------+------------+------------+----------+------------+   |
| | Deal     | Company    | Stage      | Value    | Last Update|   |
| +----------+------------+------------+----------+------------+   |
| | Deal A   | Company X  | Qualified  | $12,000  | 2 days ago |   |
| | Deal B   | Company Y  | Proposal   | $8,500   | Yesterday  |   |
| | Deal C   | Company Z  | Negotiation| $15,000  | Today      |   |
| +----------+------------+------------+----------+------------+   |
|                                                                  |
+------------------------------------------------------------------+
|                                                                  |
| AT-RISK DEALS                | UPCOMING ACTIVITIES               |
| [List of deals with no       | [Activities due in next 7 days    |
|  activity in 7+ days]        |  grouped by deal]                 |
|                              |                                   |
+------------------------------+-----------------------------------+
```

## Tab 4: Deal Tracker

```
+-----------------------------------------------------------------------------------------------------+
| SALES PIPELINE TRACKER - DEAL TRACKER                                                               |
+-----------------------------------------------------------------------------------------------------+
| [Add New Deal Button]                                [Filter Controls: Stage, Owner, Deal Size]     |
+-----------------------------------------------------------------------------------------------------+
| DEAL      | COMPANY   | CONTACT  | STAGE     | DAYS IN | VALUE   | WEIGHTED | OWNER   | EXP. CLOSE |
| NAME      | NAME      | NAME     | CURRENT   | STAGE   |         | VALUE    | NAME    | DATE       |
+-----------------------------------------------------------------------------------------------------+
| Project A | ABC Corp  | John D.  | Qualified | 5       | $12,000 | $3,000   | Tom     | 2024-05-15 |
| Service B | XYZ Inc   | Sarah M. | Proposal  | 3       | $8,500  | $5,100   | Lisa    | 2024-04-30 |
| Renewal C | 123 Ltd   | Mike P.  | Negot.    | 7       | $15,000 | $12,000  | Tom     | 2024-04-20 |
| Project D | Smith Co. | Amy R.   | Initial   | 1       | $6,200  | $620     | Lisa    | 2024-06-10 |
| Service E | Johnson   | David T. | Proposal  | 4       | $9,500  | $5,700   | John    | 2024-05-05 |
+-----------------------------------------------------------------------------------------------------+
| LEAD      | PREVIOUS  | DATE     | LAST     | NEXT    | NEXT     | PRIORITY | NOTES               |
| SOURCE    | STAGE     | ENTERED  | ACTIVITY | ACTION  | DATE     | FLAG     |                     |
+-----------------------------------------------------------------------------------------------------+
| Website   | Initial   | 04/10/24 | 04/14/24 | Demo    | 04/17/24 | Medium   | Needs custom quote  |
| Referral  | Qualified | 04/12/24 | 04/14/24 | Proposal| 04/16/24 | High     | Decision next week  |
| Existing  | Proposal  | 04/08/24 | 04/13/24 | Follow  | 04/15/24 | High     | Competitor involved |
| LinkedIn  | --        | 04/14/24 | 04/14/24 | Call    | 04/18/24 | Low      | Initial inquiry     |
| Event     | Qualified | 04/11/24 | 04/12/24 | Meeting | 04/19/24 | Medium   | Requested references|
+-----------------------------------------------------------------------------------------------------+
```

## Tab 5: Activity Log

```
+-----------------------------------------------------------------------------------------+
| SALES PIPELINE TRACKER - ACTIVITY LOG                                                   |
+-----------------------------------------------------------------------------------------+
| NEW ACTIVITY                                                                            |
+-----------------------------------------------------------------------------------------+
| Deal: [Dropdown]     | Activity Type: [Dropdown]   | Date: [Date picker]                |
| Description: [Text input field]                                                         |
| Outcome: [Text input field]                        | Next Steps: [Text input field]     |
| Follow-up Date: [Date picker]    | [Add Activity Button]                                |
+-----------------------------------------------------------------------------------------+
|                                                                                         |
| ACTIVITY HISTORY                                         [Filter Controls]              |
+-----------------------------------------------------------------------------------------+
| DATE     | DEAL      | ACTIVITY   | DESCRIPTION       | OUTCOME     | NEXT     | FOLLOW |
|          | NAME      | TYPE       |                   |             | STEPS    | UP     |
+-----------------------------------------------------------------------------------------+
| 04/14/24 | Project A | Call       | Discovery call    | Interested  | Send info| 04/17  |
| 04/14/24 | Service B | Email      | Proposal follow-up| Reviewing   | Call     | 04/16  |
| 04/13/24 | Renewal C | Meeting    | Contract review   | Questions   | Revise   | 04/15  |
| 04/12/24 | Service E | Proposal   | Sent initial quote| Received    | Follow-up| 04/19  |
| 04/11/24 | Project A | Email      | Initial contact   | Responded   | Schedule | 04/14  |
+-----------------------------------------------------------------------------------------+
|                                                                                         |
| UPCOMING ACTIVITIES                                                                     |
+-----------------------------------------------------------------------------------------+
| [Today's activities highlighted]                                                        |
| [Next 7 days grouped by date]                                                           |
| [Overdue activities highlighted in red]                                                 |
+-----------------------------------------------------------------------------------------+
```

## Tab 6: Reports

```
+-----------------------------------------------------------------------------------------+
| SALES PIPELINE TRACKER - REPORTS                                                        |
+-----------------------------------------------------------------------------------------+
| [Time Period Selector: This Month, Last Month, This Quarter, Custom]                    |
+-----------------------------------------------------------------------------------------+
|                                                |                                        |
| CONVERSION METRICS                             | PERFORMANCE TRENDS                     |
| [Stage-to-stage conversion rates visualized    | [Line charts showing:                  |
| as a funnel with percentages]                  |  - Deals created over time             |
|                                                |  - Deals closed over time              |
| Average conversion rates:                      |  - Win/loss ratio over time]           |
| - Lead to Qualified: 45%                       |                                        |
| - Qualified to Proposal: 65%                   |                                        |
| - Proposal to Negotiation: 70%                 |                                        |
| - Negotiation to Closed: 80%                   |                                        |
| - Overall lead to close: 16%                   |                                        |
|                                                |                                        |
+------------------------------------------------+----------------------------------------+
|                                                |                                        |
| TEAM PERFORMANCE                               | SOURCE EFFECTIVENESS                   |
| [Bar charts showing:                           | [Charts showing:                       |
|  - Deals by team member                        |  - Pipeline by lead source             |
|  - Close rate by team member                   |  - Conversion rate by lead source      |
|  - Activity count by team member]              |  - Average deal size by source]        |
|                                                |                                        |
+------------------------------------------------+----------------------------------------+
|                                                                                         |
| CUSTOM REPORT                                                                           |
| [Configurable report area where users can select metrics to display]                    |
|                                                                                         |
+-----------------------------------------------------------------------------------------+
```

## Tab 7: Forecast Integration

```
+-----------------------------------------------------------------------------------------+
| SALES PIPELINE TRACKER - FORECAST INTEGRATION                                           |
+-----------------------------------------------------------------------------------------+
|                                                                                         |
| This tab allows you to integrate your pipeline data with the Sales Forecast Tool.       |
|                                                                                         |
+-----------------------------------------------------------------------------------------+
|                                                                                         |
| EXPORT PIPELINE TO FORECAST                                                             |
| Time Period: [Dropdown]                       [Export Button]                           |
|                                                                                         |
| Last Export: [Date/time of last export]                                                 |
|                                                                                         |
+-----------------------------------------------------------------------------------------+
|                                                                                         |
| PIPELINE BY FORECAST MONTH                                                              |
| +------------+------------------+------------------+                                    |
| | MONTH      | PIPELINE VALUE   | WEIGHTED VALUE   |                                    |
| +------------+------------------+------------------+                                    |
| | April 2024 | $35,700          | $21,100          |                                    |
| | May 2024   | $45,500          | $19,950          |                                    |
| | June 2024  | $38,200          | $12,450          |                                    |
| | July 2024  | $26,100          | $9,150           |                                    |
| +------------+------------------+------------------+                                    |
|                                                                                         |
+-----------------------------------------------------------------------------------------+
|                                                                                         |
| FORECAST COMPARISON                                                                     |
| [Chart comparing pipeline forecast with historical forecast]                            |
|                                                                                         |
+-----------------------------------------------------------------------------------------+
|                                                                                         |
| INTEGRATION INSTRUCTIONS                                                                |
| Step-by-step guide on how to use pipeline data in the Sales Forecast Tool              |
|                                                                                         |
+-----------------------------------------------------------------------------------------+
```

## Color Coding System

```
+-----------------------------------------------------------------------------------------+
| COLOR CODING SYSTEM                                                                     |
+-----------------------------------------------------------------------------------------+
| Input cells             | Light yellow background (#FFFDE7)                             |
| Calculation cells       | Light gray background (#F5F5F5)                               |
| Navigation elements     | Blue text (#1565C0)                                           |
| Warning indicators      | Red text (#D32F2F)                                            |
| Positive indicators     | Green text (#388E3C)                                          |
+-----------------------------------------------------------------------------------------+
| Deal Stages                                                                             |
+-----------------------------------------------------------------------------------------+
| Initial Contact         | Light blue (#E3F2FD)                                          |
| Qualified               | Light cyan (#E0F7FA)                                          |
| Meeting Scheduled       | Light teal (#E0F2F1)                                          |
| Proposal Sent           | Light green (#E8F5E9)                                         |
| Negotiation             | Light lime (#F9FBE7)                                          |
| Closed Won              | Light green (#E8F5E9)                                         |
| Closed Lost             | Light red (#FFEBEE)                                           |
+-----------------------------------------------------------------------------------------+
| Priority Flags                                                                          |
+-----------------------------------------------------------------------------------------+
| High                    | Orange (#FF9800)                                              |
| Medium                  | Yellow (#FFC107)                                              |
| Low                     | Blue (#2196F3)                                                |
+-----------------------------------------------------------------------------------------+
```

## Mobile Optimization

```
+-----------------------------------------------------------------------------------------+
| MOBILE VIEW ADAPTATIONS                                                                 |
+-----------------------------------------------------------------------------------------+
| Dashboard:                                                                              |
| - Summary cards stacked vertically                                                      |
| - Charts simplified and enlarged                                                        |
| - Recent deals limited to top 3                                                         |
|                                                                                         |
| Deal Tracker:                                                                           |
| - Reduced columns (Name, Stage, Value, Owner, Next Action)                              |
| - Expandable rows for additional details                                                |
| - Larger touch targets for editing                                                      |
|                                                                                         |
| Activity Log:                                                                           |
| - Simplified entry form                                                                 |
| - Compact activity view (Date, Deal, Type, Next Step)                                   |
| - Today's activities always at top                                                      |
+-----------------------------------------------------------------------------------------+
```

## Sheet Protection Strategy

```
+-----------------------------------------------------------------------------------------+
| SHEET PROTECTION STRATEGY                                                               |
+-----------------------------------------------------------------------------------------+
| Instructions Tab:                                                                       |
| - Fully protected except navigation buttons                                             |
|                                                                                         |
| Configuration Tab:                                                                      |
| - Input cells unlocked                                                                  |
| - Formula cells locked                                                                  |
| - Structure protected                                                                   |
|                                                                                         |
| Deal Tracker Tab:                                                                       |
| - Data entry rows unlocked                                                              |
| - Formula cells locked                                                                  |
| - Filter controls unlocked                                                              |
|                                                                                         |
| Dashboard & Reports:                                                                    |
| - Mostly protected                                                                      |
| - Filter and date range controls unlocked                                               |
| - Custom report area partially unlocked                                                 |
+-----------------------------------------------------------------------------------------+
```