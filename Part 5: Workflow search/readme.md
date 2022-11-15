OfficeActivity //Table
| where TimeGenerated > ago(24h) //Pipe
| where UserId has "rodtrent" //Filter
| where RecprdType == "ExchangeItem"
| where Operation == "Send"
| project UserId, ClientIP, OriginatingServer //Control Results