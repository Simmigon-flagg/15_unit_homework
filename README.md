# 15_unit_homework
### SIEM SPL

```splunk
source="buttercupgames_email_log.csv"  Sender!=*@buttercupgames.com AND incoming_address!=10.* | stats count by  date_month, date_year, date_wday, incoming_address, Subject, Sender, Recipient  | table  incoming_address date_month date_wday date_year Subject Sender Recipient  | rename date_month as Month date_wday as Day date_year as Year  Sender as Attacker, incoming_address as IP
```
![Screenshot (154)](https://user-images.githubusercontent.com/8258629/70185360-9dc54980-16b7-11ea-8ba8-a29317e72cd5.png)
