# Amazon SNS
---
- Serverless notification service
- Offers message delivery to publishers or subscribers
- Supports application - to - application subs that include amazon SQS and other AWS services
- No message retention

##### How it works
- A *publisher* sends message to one *SNS topic*
- *Subscribers* listen to *SNS topic* notificaiton
- *Subs* get message

##### Subs can be
- HTTP/HTTPS
- Emails, SMS, mobile notifications
- SQS queues
- Lambda functions (your own integration)

