The PWC Call Center dashboard project uses several DAX measures to calculate key performance indicators (KPIs). Here are the primary measures.

### **1. Total Calls**

Calculates the volume of calls received by the center.

```dax
Total Calls = DISTINCTCOUNT(calls[call_id])

```

### **2. Total Calls Answered**

Calculates the number of calls that were successfully picked up by an agent.

```dax
Total Call Answered = 
CALCULATE(
    COUNT(calls[call_id]), 
    calls[answer] = "Y"
)

```

### **3. Call Resolve %**

Measures the percentage of answered calls that were successfully resolved.

```dax
Call Resolve % = 
VAR TotalResolveCalls = CALCULATE(COUNT(calls[call_id]), calls[resolve] = "Y")
VAR TotalAnswered = [Total Call Answered]
RETURN
DIVIDE(TotalResolveCalls, TotalAnswered, 0)

```

### **4. Call Abandon Rate %**

Calculates the percentage of incoming calls that were not answered.

```dax
Call Abundant % = 
VAR CallNotAnswered = CALCULATE(COUNT(calls[call_id]), calls[answer] = "N")
RETURN
DIVIDE(CallNotAnswered, [Total Calls], 0)

```

### **5. Speed of Answer (Avg)**

Calculates the average time (in seconds) it takes for an agent to answer a call.

```dax
Speed of Answer = 
VAR TotalSpeedDurations = SUM(calls[speed_of_answer_in_seconds])
RETURN
DIVIDE(TotalSpeedDurations, [Total Call Answered], 0)

```

### **6. Average Call Handling Time (AHT)**

Measures the average duration an agent spends talking to a customer.

```dax
Avg Call Handling Time = 
VAR TotalTalkDurations = SUM(calls[talk_durations])
RETURN
DIVIDE(TotalTalkDurations, [Total Call Answered], 0)

```

### **7. CSAT (Customer Satisfaction Score)**

Converts the 1-5 rating scale into a percentage score.

```dax
CSAT = 
VAR TotalRatings = SUM(calls[satisfaction_rating])
VAR NumberOfRatings = COUNT(calls[satisfaction_rating])
RETURN
DIVIDE(TotalRatings, (NumberOfRatings * 5), 0)

```

### **8. Last Call Received (Dynamic Title)**

Used to show the freshness of the data on the dashboard.

```dax
Last Call Received = "Last Call: " & MAX(calls[date_time])

```

These measures are organized into a dedicated **Measures Table** to keep the Power BI model clean and efficient.
