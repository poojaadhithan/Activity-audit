# EXPERIMENT 4 - AUDITING CLOUD ACTIVITY USING AWS CLOUDTRAIL

## OBJECTIVE

To audit and monitor cloud activity in AWS using AWS CloudTrail by viewing and analyzing recorded AWS events and identifying important audit information such as user identity, event name, event time, AWS service, region, and operation status.

---

## REQUIREMENTS

* AWS Account
* Web Browser
* Internet Connection
* Amazon S3 Access
* AWS CloudTrail

---

# PART A - ACCESS AWS CLOUDTRAIL

## Step 1: Login to AWS

1. Open the AWS Management Console.
2. Sign in using your AWS account.
3. In the AWS search bar, type **CloudTrail**.
4. Select **AWS CloudTrail**.
   
<img width="1600" height="881" alt="WhatsApp Image 2026-09-12 at 12 47 51 PM" src="https://github.com/user-attachments/assets/e0665336-af27-4e00-bb11-bd7e0106dc8c" />




## Step 2: Open Event History

1. In the CloudTrail navigation menu, select **Event history**.
2. CloudTrail displays recent AWS activity.
3. Review the available events.

The Event History page displays information such as:

* Event time
* Username
* Event name
* Event source
* Resource type
* Resource name


<img width="1600" height="890" alt="WhatsApp Image 2026-09-12 at 12 53 33 PM" src="https://github.com/user-attachments/assets/39081a88-00df-416c-b24a-4c3cdf3bfceb" />



---

# PART B - ANALYZE A CLOUDTRAIL EVENT

## Step 3: Select an Event

From the Event History list, an S3-related event was selected.

The event selected was:

**CreateBucket**

The event details were opened and analyzed.


<img width="1600" height="881" alt="WhatsApp Image 2026-09-12 at 12 55 11 PM" src="https://github.com/user-attachments/assets/afe083da-18f4-43f7-8243-ba5df8280911" />



---

## Step 4: Analyze the CreateBucket Event

The **CreateBucket** event indicates that an Amazon S3 bucket creation operation occurred.

| Parameter        | Observation                           |
| ---------------- | ------------------------------------- |
| **Event Time**   | August 04, 2026, 14:05:35 (UTC+05:30) |
| **User Name**    | root                                  |
| **Event Name**   | CreateBucket                          |
| **Event Source** | s3.amazonaws.com                      |
| **AWS Region**   | us-east-1                             |
| **Read-only**    | false                                 |
| **Error Code**   | -                                     |
| **Activity**     | S3 bucket creation                    |

### Meaning of Important Fields

| Field            | Meaning                                                                    |
| ---------------- | -------------------------------------------------------------------------- |
| **Event Time**   | Time at which the activity occurred                                        |
| **User Name**    | User or identity associated with the activity                              |
| **Event Name**   | AWS operation that was performed                                           |
| **Event Source** | AWS service that generated the event                                       |
| **AWS Region**   | Region where the activity occurred                                         |
| **Read-only**    | Indicates whether the event was only a read operation or involved a change |
| **Error Code**   | Indicates whether an error occurred during the operation                   |

---

# PART C - IDENTIFY ANOTHER CLOUDTRAIL EVENT

## Step 5: Select Another Event

1. Return to **CloudTrail → Event history**.
2. Select another event.
3. Open its details.
4. Record the important fields.

The second event selected was:

**AutomatedDefaultVpcCreation**

<img width="1600" height="881" alt="WhatsApp Image 2026-09-12 at 1 00 48 PM" src="https://github.com/user-attachments/assets/29859974-64f2-4028-9005-1357d8c16734" />



---

## Step 6: Analyze the Second Event

| Parameter        | Observation                           |
| ---------------- | ------------------------------------- |
| **Event Time**   | August 04, 2026, 14:17:34 (UTC+05:30) |
| **User Name**    | System/ AWS service                                |
| **Event Name**   | AutomatedDefaultVpcCreation           |
| **Event Source** | ec2.amazonaws.com                     |
| **AWS Region**   | ap-south-1                            |
| **Read-only**    | false                                 |
| **Error Code**   | -                                     |
| **Activity**     | Automated default VPC creation        |


---

# PART D - COMPARE THE EVENTS

## Step 7: Prepare the Audit Comparison

The two CloudTrail events were compared as follows:

| Parameter        | Event 1                   | Event 2                        |
| ---------------- | ------------------------- | ------------------------------ |
| **Event Time**   | August 05, 2026, 11:21:44 | August 04, 2026, 14:17:34      |
| **User Name**    | root                      | System / ec2.amazonaws.com     |
| **Event Name**   | CreateBucket              | AutomatedDefaultVpcCreation     |
| **Event Source** | s3.amazonaws.com          | ec2.amazonaws.com               |
| **AWS Region**   | ap-south-1                | ap-south-1                      |
| **Read-only**    | false                     | false                           |
| **Error Code**   | -                         | -                               |
| **Activity**     | S3 bucket creation        | Automated VPC creation          |

---

# PART E - SECURITY AUDIT ANALYSIS

## Step 8: Identify Who, What, When and Where

### Event 1 — CreateBucket

| Question    | Answer                            |
| ----------- | --------------------------------- |
| **WHO?**    | root                              |
| **WHAT?**   | CreateBucket — S3 bucket creation |
| **WHEN?**   | August 05, 2026, 11:21:44         |
| **WHERE?**  | us-east-1                         |
| **RESULT?** | Successful — No error code        |

### Event 2 — AutomatedDefaultVpcCreation

| Question    | Answer                                                       |
| ----------- | ------------------------------------------------------------ |
| **WHO?**    | root                                                        |
| **WHAT?**   | AutomatedDefaultVpcCreation — Automated VPC creation        |
| **WHEN?**   | August 05, 2026, 11:30:23                                    |
| **WHERE?**  | us-east-1                                                   |
| **RESULT?** | Successful — No error code                                   |

---

# Step 9: Final Audit Table

| Parameter      | Event 1                   | Event 2                        |
| -------------- | ------------------------- | ------------------------------ |
| **Event Time** | Aug 04, 2026, 13:55:40    | Aug 04, 2026, 14:17:34         |
| **User**       | root                      | System / EC2 service           |
| **Event Name** | CreateBucket              | AutomatedDefaultVpcCreation    |
| **Service**    | Amazon S3                 | Amazon EC2                     |
| **Region**     | ap-south-1                | ap-south-1                     |
| **Read-only**  | false                     | false                          |
| **Result**     | Successful                | Successful                     |
| **Activity**   | S3 bucket creation        | Automated VPC creation         |

---

# RESULT

The cloud activities in AWS were successfully audited using **AWS CloudTrail Event History**. Two different AWS events, **CreateBucket** and **AutomatedDefaultVpcCreation**, were examined and compared based on event time, user identity, event name, event source, AWS Region, read-only status, and error status.

The experiment demonstrated how **AWS CloudTrail provides an audit trail for monitoring, accountability, security auditing, and investigation of cloud activities**.
