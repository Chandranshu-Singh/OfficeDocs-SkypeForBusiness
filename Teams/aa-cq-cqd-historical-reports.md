---
title: Auto Attendant & Call Queue Historical Report
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: 
  - M365-voice
search.appverid: MET150
audience: Admin
appliesto: 
  - Skype for Business
  - Microsoft Teams
ms.localizationpriority: medium
f1.keywords: 
  - CSH
ms.custom: 
  - Reporting
  - ms.teamsadmincenter.directrouting.cqd
  - ms.lync.lac.ToolsCallQualityDashboard
description: Learn about how to use Teams Auto Attendant & Call Queue Historical Report Power BI report to view Auto Attendant and Call Queue historical data.
---
# Auto Attendant & Call Queue Historical Report

This Power BI template provides three reports that allow organizations to report on the number of calls being processed by auto attendants and call queues.  It also provides agent performance insights.

## V3.0.3 published on November 8, 2022

The Teams Auto Attendant & Call Queue Historical Report Power BI template provides the following three reports:

- The Auto Attendant report shows analytics for calls coming into your auto attendants.
- The Call Queue report shows analytics for calls coming into your call queues.
- The Agent Timeline report shows a timeline view of agents being active in call queue calls.

These reports use data from the Voice Applications Analytics Collector (VAAC) service.

>[!NOTE]
> Historical data collection is in progress across all regions.  Thirty days of historical data will be available at different times, with all regions having a full 30 days of data no later than November 25, 2022.

## V3.x.x Prerequisites

### Power BI Desktop
You need to have Power BI Desktop installed. You can install and use the free version from the [Microsoft Windows Store](https://aka.ms/pbidesktopstore).

The minimum compatible version is 2.85.681.0 (September 2020).

### Permissions to access the CQD pipeline

While this version of the reports doesn't use the Call Quality Dashboard (CQD) data pipeline, the account used to view the historical data still requires access to the Call Quality Dashboard. For more information, see [CQD access role](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).
- This requirement will be removed in a future release.

## V3.x.x Installation 

The following steps assume you've already installed Power BI Desktop on your computer and that your account has the necessary permissions to access the CQD data pipeline.

Perform the following steps:

1. Download and save the [Teams Auto Attendant & Call Queue Historical Reports V3.0.3.zip](https://www.microsoft.com/download/details.aspx?id=104623) file on your computer.

1. Open the zip file.

1. Open the `Teams Auto Attendant & Call Queue Historical Reports V3.0.3.pbit` template file. Power BI Desktop should launch.

1. You'll be prompted to select the **Data Source**.  Select the `api.interfaces.records.teams.microsoft.com` entry.

  :::image type="content" source="media/aa-cq-historical-report-01-v300.png" alt-text="Screenshot selecting the api.interfaces.records.teams.microsoft.com Data Soure":::

1. You'll be prompted to sign in with an account. Select **Organizational account**, and then select **Sign in**.

  :::image type="content" source="media/aa-cq-historical-report-03-v300.png" alt-text="Screenshot showing login for V3.0.0.":::

1. Select **Connect**, and the data will refresh.

> [!NOTE]
> If you're using v1.63 or earlier, you may encounter an error when v3.x.x tries to retrieve the data from VAAC.  To resolve this error, it's necessary to clear any previous credentials from Power BI.
> 
> 1. Open the v3.x.x template to clear the error. 
> 1. Select **File** > **Options & Settings** > **Data source settings**.
> 1. Select the drop down for **Clear Permissions**, and then select **Clear All Permissions**.
> 1. Close the template after they're cleared, and restart Power BI. You'll be asked to authorize again. 

## V1.63 published on August 24, 2022

> [!IMPORTANT]
> Support for the V1.63 template will end on November 21, 2022.

The **Teams Auto Attendant & Call Queue Historical Report Power BI Template** provides the following three reports:

- The Auto Attendant report shows analytics for calls coming into your auto attendants.
- The Call Queue report shows analytics for calls coming into your call queues.
- The Agent Timeline report shows a timeline view of agents being active in call queue calls.

These reports use data from the [Call Quality Dashboard (CQD)](CQD-Power-BI-query-templates.md) data store. 

## V1.63 Prerequisites

### Power BI Desktop
You need to have Power BI Desktop installed. You can install and use the free version from the [Microsoft Windows Store](https://aka.ms/pbidesktopstore).

The minimum compatible version is 2.85.681.0 (September 2020).

### Permissions to access the CQD pipeline

The account you use to view the historical report needs to have permissions to access the CQD data pipeline. For more information, see [CQD access role](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

## V1.63 Installation 

The following steps assume you've already installed Power BI Desktop on your computer and that your account has the necessary permissions to access the CQD data pipeline.

Perform the following steps:

1. Download and save the [CQD Power BI Query Templates](https://www.microsoft.com/download/details.aspx?id=102291) zip file on your computer.

1. Open the zip file.

1. Open the `CQD Teams Auto Attendant & Call Queue Historical Report V1.60.pbit` template file. Power BI Desktop should launch.

1. You'll be prompted to select the CQD data pipeline region. Select the region where your tenant is located.

  :::image type="content" source="media/aa-cq-historical-report-01-v163.png" alt-text="Screenshot selecting the CQD data pipeline region.":::

1. The region where your tenant is located can be obtained by using the [Get-CsTenant](/powershell/module/skype/get-cstenant) cmdlet.

    ```powershell
    (Get-CsTenant).ServiceInstance


    microsoftcommunicationsonline/noam-4a-s7
    ```

    1. The region will be displayed after the **/** as in the above example where the region is `noam`.

 1. The report will launch with sample data.
 
 1. To see your own data, select **Refresh** on the **Home** tab under **Queries** in Power BI Desktop.

   :::image type="content" source="media/aa-cq-historical-report-02-v163.png" alt-text="Screenshot selecting the refresh option.":::

1. You'll be prompted to sign in. Select **Organizational account**, and then select **Sign in**.

  :::image type="content" source="media/aa-cq-historical-report-03-v163.png" alt-text="Screenshot showing login for V1.63.":::

1. Select **Connect**, and the data will refresh.

## Data latency and AA & CQ analytics

Data is typically available within 30 minutes of the call completing; however, there are occasions where it may take several hours for data to appear. 

You'll have to refresh the data to see any new data.

## Customization 

You can customize certain visualization aspects of the reports, such as adding or removing fields to be shown in the various visualizations, changing chart type, and so on.

The report contains all the data metrics currently available.

### Change color schema 

The following steps assume you've already completed the installation steps.

Perform the following steps:

- Select **View tab** on the ribbon.

  :::image type="content" source="media/aa-cq-historical-report-04.png" alt-text="Screenshot selecting view tab to change color scheme.":::

- Select the color schema from the drop-down list.

  :::image type="content" source="media/aa-cq-historical-report-05.png" alt-text="Screenshot showing various color schemes.":::
  
## Auto attendant and call queue historical reports definitions

### Cloud Auto Attendant Analytics report

#### Report description

|Report Section                          |Description                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|Incoming Call Source<sup>1</sup>        |Distribution of calls by Internal/External call source            |
|Directory Search Method                 |Distribution of calls by search type                              |
|Caller Action Count                     |Distribution of calls by number action used during the call       |
|Average Seconds in AA                   |Average number of seconds callers spend in the AA                 |
|Average Caller Actions                  |Average number of actions callers perform in the AA               |
|Call Results                            |Distribution of calls by final call state                         |
|Lower section of report                 |Call flow breakdown                                               |



#### Report to CQD table and field mapping

|Report Tab            |Report Table Name     |Source Table Name            |Global Filter                          |
|:---------------------|:---------------------|:----------------------------|:--------------------------------------|
|Auto Attendant        |fAutoAttendant        |AutoAttendant                |None                                   |

|Report Section                                  |Field(s) Used                              |Filters Applied     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|Date selector                                   |AAStartTime                                |None                |
|Time Range selector                             |AAStartHour                                |None                |
|Auto Attendant                                  |AA Name                                    |None                |
|Incoming Call Source<sup>1</sup>                |Call Type<br>Sum of TotalCallCount (Measure) |External Calls: Call Type is External<br>Internal Calls: Call Type is Internal |
|Directory Search Method                         |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod is abs_search_dtmf or abs_search_name    |
|Caller Action Count                             |AACallerActionCount<br>TotalCallCount      |None                                                             |
|Average Seconds in AA                           |AAChainDuration (Measure)                  |None                                                             |
|Average Caller Actions                          |AACallerActionCount (Measure)              |None                                                             |
|Call Results                                    |AACallResult<br>AACallResultLegend<br>TotalCallCount             |None                                       |
|Lower section of report                         |AA Name<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>Call Type<br>MM-DD<br>TotalCallCount |None       |

#### fAutoAttendant CQD fields description

|Name                                    |Data Type                |Description                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA Name                                 |Text                     |Name of resource account attached to Auto Attendant<br><br>If the full Resource Account name is **aa_test@microsoft.com**, then this value will be: **aa_test** |
|AACallerActionCount                     |Whole number             |Summarize: Sum<br>Count of actions selected by caller in Auto Attendant during the call  |
|AACallerActionCount  (Measure)          |Whole number             |Same as above except will be 0 if no calls instead of blank                              |
|AACallFlow                              |Text                     |Encapsulates the different states of Auto Attendant Call--possible values:<br><br>§ abs_search<br>§ announcement<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |Text                     |Final call result--possible values:<br><br>§ failed_to_establish_media (the media portion of the call couldn't be established)<br>§ failover_to_operator (call transferred to operator typically due to a system error)<br>§ oaa_chain_too_long (too many legs in the AA)<br>§ oaa_session_too_long (AA session has lasted too long)<br>§ service_declined (AA didn't accept the call)<br>§ service_terminated (AA configuration disconnects the call or call hung up)<br>§ terminated_automatic_selection (AA configuration disconnects the calls)<br>§ terminated_no_operator (call terminated due to error no operator defined) <br>§ terminated_transfer_failed (call terminated as transfer failed - typically to external number)<br>§ transfer_in_progress (AA->AA transfer)<br>§ transferred_to_operator (call was transferred to operator - typically due to user error)<br>§ transferred_to_receptionist (same as transferred_to_operator)<br>§ transferred_to_self (call was returned to the start of the AA - typically from a menu announcement option)<br>§ transferred_to_shared_voicemail (call was transferred to shared voicemail)<br>§ transferred_to_user (call was transferred to a user - includes call queues)<br>§ unknown (an unknown condition has occurred)<br>§ user_terminated (caller hung up) |
|AA Call Legend                          |Text                     |Sets up legend items based on AACallResult                               |
|AAChainDuration                         |Decimal number           |Summarize: Sum<br>Duration of call in Auto Attendant                     |
|AAChainDuration (Measure)               |Decimal number           |Same as above except will be 0 if no calls instead of blank              |
|AAChainIndex                            |Text                     |                                                                         |
|AAConnectivityType                      |Text                     |Type of call--possible values:<br><br>§ ExternalCall<br>§ InternalCall |
|AACount                                 |Text                     |Number of Auto Attendants involved in call                               |
|AADirectorySearchMethod                 |Text                     |Last address book search method--possible values:<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartHour                             |Decimal number           |Auto Attendant call start hour                                           |
|AAStartTime                             |Date/time                |Auto Attendant call start time                                           |
|AATransferAction                        |Text                     |Call transfer target type--possible values:<br><br>§ application - voice application entity<br>§ external_pstn<br>§ hunt_group - Call Queue entity<br>§ orgaa - Auto Attendant entity<br>§ shared_voicemail<br>§ unknown<br>§ user |
|Call Type<sup>1</sup>                   |Text                     |Type of call--possible values:<br><br>§ External<br>§ Internal           |
|IsAAInvolved                            |Text                     |Always 1                                                                 |
|MM-DD                                   |Text                     |Auto Attendant call month-day                                            |
|PSTNMinutes                             |Whole number             |Summarize: Sum<br>Total minute usage                                     |
|TotalCallCount                          |Whole number             |Summarize: Sum<br>Always 1 - used to provide sum of all calls            |
|Sum of TotalCallCount (Measure)         |Whole number             |Same as above except will be 0 if no calls instead of blank              |


### Cloud Call Queue Analytics report

#### Report description

|Report Section                          |Description                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|Incoming Call Source<sup>1</sup>        |Distribution of calls by Internal/External call source             |
|Average Wait Time (seconds)             |Wait time for answered and abandoned calls                          |
|Call Volume and Agent Opt-in Count      |Distribution of calls by call queues / Maximum agent opt-in count  |
|Call Results                            |Distribution of calls by call result                               |
|Abandoned Calls                         |Distribution of abandoned calls by call queues                     |
|Average Session Length (seconds)        |Call length in seconds grouped by call result                      |
|Call Overflow/Timeout Destinations      |Distribution of calls that timed out or overflowed                 |


#### Report to CQD table and field mapping

|Report Tab            |Report Table Name                                   |Source Table Name                               |Global Filter       |
|:---------------------|:---------------------------------------------------|:-----------------------------------------------|:-------------------|
|Call Queue            |fCallQueueAnalytics<br>fCallQueueFinalStateAction   |CallQueueAnalytics<br>CallQueueFinalStateAction |None                |

|Report Section                      |Table -> Field(s) Used                |Filters Applied       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|Date selector                       |fCallQueueAnalytics -> Date           |None                  |
|Time Range selector                 |fCallQueueAnalytics -> CQHour         |None                  |
|Call Queue Resource Account         |fCallQueueAnalytics -> CQ Name        |None                  |
|Incoming call source<sup>1</sup>    |fCallQueueAnalytics -> Sum of Call Count (Measure)<br>fCallQueueAnalytics -> Call Type    |External Calls: Call Type is External<br>Internal Calls: Call Type is Internal |
|Avg Wait Time (seconds)-Before Answered |fCallQueueFinalStateAction -> Avg of Average CQ Duration (Measure) |Call Queue Call Result is agent_joined_conference or transferred_to_agent|
|Avg Wait Time (seconds)-Before Abandoned |fCallQueueFinalStateAction -> Avg of Average Call Duration (Measure) |Call Queue Call Result isn't agent_joined_conference, transferred_to_agent, overflown, timed_out |
|Call Volume and Agent Opt-In Count   |fCallQueueAnalytics -> Call Count<br>fCallQueueAnalytics -> Call Queue Agent Opt In Count<br>fCallQueueAnalytics -> CQ Name<br>fCallQueueAnalytics -> Date |None |
|Abandoned Calls                     |fCallQueueAnalytics -> Date<br>fCallQueueAnalytics -> TotalCallCount | Call Queue Call Result Legend is Abandoned |
|Average Session Length (seconds)    |fCallQueueFinalStateAction -> Average Call Queue Duration (Sec)<br>Call Queue Call Result Legend |Average Call Queue Duration (Sec) > 0 |
|Call Overflow/Timeout Destinations  |fCallQueueAnalytics -> Call Count<br>fCallQueueAnalytics -> Call Queue Target Type<br>fCallQueue Target Type Legend |Call Queue Target Type Legend doesn't contain Abandoned and Agent Answered |


#### fCallQueueAnalytics CQD fields description

|Name                                    |Data Type                |Description                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|Call Count                              |Whole number             |Summarize: Sum<br>Number of calls                                          |
|Call Queue Agent Count                  |Whole number             |Summarize: Sum<br>Number of agents configured in the call queue            |
|Call Queue Agent Opt In Count           |Whole number             |Summarize: Sum<br>Number of agents opted-in to the call queue              |
|Call Queue Call Result                  |Text                     |Call queue call final state--possible values:<br><br>§ agent_joined_conference (answered conference mode calls)<br>§ declined<br>§ disconnected<br>§ error<br>§ failed<br>§ invalid<br>§ overflown (overflow condition met)<br>§ timed_out (timeout condition met)<br>§ transferred_to_agent (answered transfer mode calls {default}) |
|Call Queue Call Result Legend           |Text                     |Sets up legend items based on Call Queue Result                             |
|Call Queue Target Type                  |Text                     |***Call redirection target type--possible values:***<br><br>§ ApplicationEndpoint<br>§ Mailbox<br>§ Other<br>§ User |
|Call Queue Target Type Legend           |Text                     |Sets up legend items based on Call Queue Target Type                        |
|Call Type<sup>1</sup>                   |Text                     |Type of call--possible values:<br><br>§ External<br>§ Internal             |
|CQ Name                                 |Text                     |Name of resource account attached to Call Queue<br><br>If the full Resource Account name is **cq_test@microsoft.com**, then this value will be: **cq_test** |
|CQ Hour                                 |Whole Number             |Call queue call start hour                                                 |
|Date                                    |Date/time                |Call queue call start date and time (hour)                                 | 
|DateTimeCQName                          |Text                     |Unique key for filtering on fCallQueueFinalStateAction                     |
|PSTN Connectivity Type                  |Text                     |Type of call--possible values:<br><br>§ ExternalCall<br>§ InternalCall     |
|PSTN Total Minutes                      |Whole number             |Summarize: Sum<br>Total minutes usage for PSTN calls                       |
|Sum of Call Count (Measure)             |Whole number             |Same as Call Count however will be 0 when no call                          |
|TotalCallCount (Measure)                |Whole Number             |Summarize: Sum<br>Call Count                                                |


#### fCallQueueFinalStateAction  CQD fields description

|Name                                    |Data Type                |Description                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|Average Call Duration (Seconds)         |Decimal number           |Summarize: Sum<br>Average call duration in seconds for abandoned calls    |
|Average Call Queue Duration (Sec)       |Decimal number           |Summarize: Sum<br>Average waiting in seconds for answered calls           |
|Avg of Average Call Duration (Measure)  |Whole number             |Same as Average Call Duration (Seconds) however will be 0 when no calls   |
|Avg of Average CQ Duration (Measure)    |Whole number             |Same as Average Call Queue Duration (Sec) however will be 0 when no calls |
|Call Count                              |Whole number             |Summarize: Sum<br>Number of calls                                         |
|Call Queue Call Result                  |Text                     |Call queue call final state--possible values:<br><br>§ agent_joined_conference (answered conference mode calls)<br>§ declined<br>§ disconnected<br>§ error<br>§ failed<br>§ invalid<br>§ overflown (overflow condition met)<br>§ timed_out (timeout condition met)<br>§ transferred_to_agent (answered transfer mode calls {default} |
|Call Queue Call Result Legend           |Text                     |Sets up legend items based on Call Queue Call Result                      |
|Call Queue Final State Action           |Text                     |Call queue final action--possible values:<br><br>§ disconnect (timed_out calls)<br>§ disconnect_with_busy (overflown calls)<br>§ failed_to_accept_call<br>§ forward<br>§ shared_voicemail<br>§ other<br>§ voicemail                |
|CQ Name                                 |Text                     |Name of resource account attached to Call Queue<br><br>If the full Resource Account name is **cq_test@microsoft.com**, then this value will be: **cq_test** |
|Date                                    |Date/time                |Call Queue call start date and time (hour)                                 |
|DateTimeCQName                          |Text                     |Unique key for filtering on fCallQueueFinalStateAction                     |
|IsAbandoned                             |True/false               |True if call isn't answered by an agent                                   |


### Cloud Call Queue Agent Timeline report

#### Report description

|Report Section                                          |Description                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|Number of Calls by Agent                                |Distribution of calls by call queue and agent                |
|Distribution by Agent and all Queue                     |Distribution of calls by agent and call queue                |
|Table (bottom right)                                    |Distribution of calls by agent with average and total call duration |
|Average Call Duration (seconds) by Agent                |Average duration (seconds) of call by agent                  |

#### Report to CQD table and field mapping

|Report Tab            |Report Table Name           |Source Table Name         |Global Filter       |
|:---------------------|:---------------------------|:-------------------------|:-------------------|
|Agent Timeline        |fAgentTimelineAnalytics     |fAgentTimelineAnalytics   |None                |


|Report Section                                |Field(s) Used                         |Filters Applied       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|Date selector                                 |DateTime                              |None                  |
|Agent Username selector                       |Agent Name                            |None                  |
|Call Queue Resource Accounts selector          |CQ Name                               |None                  |
|Number of Calls by Agent                      |Agent Name<br>Call Count<br>Hour      |None                  |
|Distribution by Agent and Call Queue          |Agent Name<br>Average Calls Duration (Seconds)<br>Call Count<br>CQ Name |None                      |
|Bottom Left                                   |Agent Name<br>Average Call Duration (Seconds)<br>Call Count<br>Call Duration (Minute)<br>CQ Name<br>Hour<br>MM-DD | None |
|Average Call Duration (Seconds) by Agent      |Agent Name<br>Average Call Duration (Seconds) | None |

#### fAgentTimelineAnalytics CQD fields description

|Name                                    |Data Type                |Description                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|Agent Name                              |Text                     |User UPN<br>If the full username is **user@microsoft.com**, then this value will be: **user** |
|Average Call Duration (Seconds)         |Decimal number           |Summarize: Sum<br>The average duration of answered call queue calls in seconds |
|Call Count                              |Whole number             |Summarize: Sum<br>Number of calls answered by the agent     |
|Call Duration (Minutes)                 |Whole number             |Summarize: Sum<br>Total call duration of answered call queue calls in minutes (rounded down to nearest minute)  |
|CQ Name                                 |Text                     |Name of resource account attached to Call Queue<br><br>If the full Resource Account name is **cq_test@microsoft.com**, then this value will be: **cq_test** |
|Date                                    |Date                     |Date of call                                             |
|DateTime                                |DateTime                 |Date of call                                             |
|Hour                                    |Whole number             |Hour of call                                             |
|MM-DD                                   |Text                     |Month and day of call                                    |


> [!NOTE]
> When a call arrives at the first call queue, if the number of calls already waiting in that queue has reached the **Call overflow handling** limit and if the redirect option sends new calls to a second call queue, then the agents in the second call queue will be shown as being in the first call queue on this report. 

## Known issues

- Call queue and auto attendants are shown by resource account's ID instead of call queue/auto attendant names.  To show all the traffic for an auto attendant or call queue, you must select all the resource accounts assigned to the auto attendant or call queue.

- Only 28 days of history are available in the dashboard as call queue/auto attendant data is considered personal data and is subject to data privacy retention policies.

- In some scenarios, the agent answered call count on the **Cloud Call Queue Agent Timeline** report may be different than the number of calls shown in the Teams client call history. The Teams client call history is correct. Support is investigating but there's no estimated time to repair available at this time.

- <sup>1</sup> **Incoming call source** in the auto attendant and call queue graphs show the final call leg source rather than the initial call leg source. For example, if an auto attendant receives an external call and transfers the call to another auto attendant or call queue, the **Incoming call source** will be reported as Internal.

## Version history

|Version  |Date Published     |Filename                                                           |Description                                         |
|:--------|:------------------|:------------------------------------------------------------------|:---------------------------------------------------|
|3.0.3    |November 8, 2022   |Teams Auto Attendant & Call Queue Historical Reports V3.0.3        |Refer to:<br>CQD Teams Auto Attendant & Call Queue Historical Reports - Change Log.docx in the downloaded zip file for a list of changes                                                                             |
|3.0.1    |October 26, 2022   |Teams Auto Attendant & Call Queue Historical Reports V3.0.1        |Removed testing data source entry                   |
|3.0.0    |October 25, 2022   |Teams Auto Attendant & Call Queue Historical Reports V3.0.0        |New backend data source                             |
|1.63     |August 24, 2022    |CQD Teams Auto Attendant & Call Queue Historical Report V1.63.pbit |Refer to:<br>CQD Teams Auto Attendant & Call Queue Historical Reports - Change Log.docx in the downloaded zip file for a list of changes                                                                             |
|1.60     |July 22, 2022      |CQD Teams Auto Attendant & Call Queue Historical Report V1.60.pbit |Refer to:<br>CQD Teams Auto Attendant & Call Queue Historical Reports - Change Log.docx in the downloaded zip file for a list of changes                                                                             |
|1.00     |November 5, 2020   |CQ and AA combined Analytics 20201105.pbit                         |Initial release                                     |

