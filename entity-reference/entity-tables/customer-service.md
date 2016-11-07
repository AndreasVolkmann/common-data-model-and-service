---
title: "Customer service reference | Common Data Model"
description: "The customer service entities manage issues from your customers, including tracking, escalation, and documentation."
author: "robinarh"
manager: "robinarh"
ms.date: "11/03/2016"
ms.topic: "topic"
ms.prod: ""
ms.service: "CommonDataService"
ms.technology: "CommonDataService"
keywords: ""
audience: "Developer, IT Pro"
ms.assetid: "ddd9b0a1-bd9e-46a9-bea0-ba021cf2f219"
---

# Customer service reference 
## Case (Case) Entity 
A problem, question, or request encountered by a customer on a product, service or interaction that requires support intervention. 

Field | Description
---|---
Account | Lookup: Account
ArrivalDate | Data: DateTime<br>Required, Searchable
CaseId<br>Primary key | Number sequence: <br>Unique, Searchable
Category | Data: Picklist<br>Required
CloseDate | Data: DateTime<br>Searchable
Comment | Data: MultilineText
CurrentAssignedSupportWorker | Lookup: Worker
CurrentContact | Lookup: Contact<br>Required
CustomerSatisfactionCode | Data: Picklist
Description | Data: Text<br>Maximum length: 255
Name | Data: Text<br>Required, Maximum length: 60<br>Description: Case name
OriginCode | Data: Picklist<br>Required<br>Description: Origin
ParentCase | Lookup: Case
Severity | Data: Picklist<br>Required
SolutionType | Data: Picklist
Status | Data: Picklist<br>Required

###Field groups

Field group | Description | Fields
---|---|---
DefaultCreate|DefaultCreate field group|Name<br>Category<br>Status<br>Severity<br>ArrivalDate<br>Description<br>OriginCode<br>CurrentContact<br>ParentCase<br>Account<br>CustomerSatisfactionCode
DefaultList|DefaultList field group|CaseId<br>Name<br>Category<br>Status<br>Severity<br>ArrivalDate
DefaultCard|DefaultCard field group|CaseId<br>Name<br>Status<br>Severity
DefaultDetails|DefaultDetails field group|CaseId<br>Name<br>Category<br>Status<br>Severity<br>ArrivalDate<br>Description<br>OriginCode<br>CurrentContact<br>ParentCase<br>Account<br>CustomerSatisfactionCode<br>CloseDate<br>SolutionType<br>Comment
DefaultLookup|DefaultLookup field group|CaseId<br>Name<br>Category<br>Status<br>Severity
DefaultReport|DefaultReport field group|CaseId<br>Name<br>Category<br>Status<br>Severity<br>ArrivalDate<br>Description<br>OriginCode<br>CurrentContact<br>ParentCase<br>Account<br>CustomerSatisfactionCode<br>CloseDate<br>SolutionType
DefaultIdentification|DefaultIdentification field group|CaseId<br>Name
## CaseActivity (Case activity) Entity 
Actions performed by support worker or customer that must be logged for a �case; for example, contacts, escalations, and case status changes. 

Field | Description
---|---
BeginDate | Data: DateTime<br>Required, Searchable
CaseSeverity | Data: Picklist<br>Required<br>Description: Current case severity
CaseStatus | Data: Picklist<br>Required<br>Description: Current case status
Comment | Data: MultilineText
Contact | Lookup: Contact
ContactType | Data: Picklist
Description | Data: Text<br>Maximum length: 255
EndDate | Data: DateTime<br>Searchable
HasKBArticle | Data: Boolean<br>Required<br>Description: Has KB article(s)
IsReassignment | Data: Boolean<br>Required
IsSeverityChange | Data: Boolean<br>Required<br>Description: Is severity changed
IsStatusChange | Data: Boolean<br>Required<br>Description: Is status changed
PriorCaseSeverity | Data: Picklist
PriorCaseStatus | Data: Picklist
ReassignedComment | Data: Text<br>Maximum length: 255
ReassignedFromCaseWorker | Lookup: Worker
ReassignedReason | Data: Picklist<br>Description: Case reassigned reason
Sequence | Data: Integer<br>Required
SupportCase<br>Primary key | Lookup: Case<br>Required
SupportWorker | Lookup: Worker
Type | Data: Picklist<br>Required

###Field groups

Field group | Description | Fields
---|---|---
DefaultCreate|DefaultCreate field group|SupportCase<br>Sequence<br>Type<br>BeginDate<br>Description<br>Contact<br>ContactType<br>CaseSeverity<br>CaseStatus<br>HasKBArticle<br>IsReassignment<br>IsSeverityChange<br>IsStatusChange
DefaultList|DefaultList field group|SupportCase<br>Sequence<br>Type<br>BeginDate<br>Description<br>CaseSeverity<br>CaseStatus
DefaultCard|DefaultCard field group|SupportCase<br>Sequence<br>Type<br>BeginDate
DefaultDetails|DefaultDetails field group|SupportCase<br>Sequence<br>Type<br>BeginDate<br>Description<br>Contact<br>ContactType<br>CaseSeverity<br>CaseStatus<br>Comment
DefaultLookup|DefaultLookup field group|SupportCase<br>Sequence<br>Type<br>BeginDate<br>Description
DefaultReport|DefaultReport field group|SupportCase<br>Sequence<br>Type<br>BeginDate<br>Description<br>Contact<br>ContactType<br>CaseSeverity<br>CaseStatus<br>HasKBArticle<br>IsReassignment<br>IsSeverityChange<br>IsStatusChange
DefaultIdentification|DefaultIdentification field group|SupportCase<br>Sequence<br>Description
## CaseActivityKBArticle (Case activity KB article) Entity 
Associates a KB article with a case activity. 

Field | Description
---|---
ArticleValue | Data: Integer<br>Required
CaseActivity<br>Primary key | Lookup: CaseActivity<br>Required
Description | Data: Text<br>Maximum length: 255
KBArticle | Lookup: KBArticle<br>Required
KBArticleName | Data: Text<br>Maximum length: 60

###Field groups

Field group | Description | Fields
---|---|---
DefaultCreate|DefaultCreate field group|CaseActivity<br>KBArticle<br>Description<br>KBArticleName<br>ArticleValue
DefaultList|DefaultList field group|CaseActivity<br>KBArticle<br>Description<br>KBArticleName
DefaultCard|DefaultCard field group|CaseActivity<br>KBArticle<br>KBArticleName
DefaultDetails|DefaultDetails field group|CaseActivity<br>KBArticle<br>Description<br>KBArticleName<br>ArticleValue
DefaultLookup|DefaultLookup field group|CaseActivity<br>KBArticle<br>Description
DefaultReport|DefaultReport field group|CaseActivity<br>KBArticle<br>Description<br>KBArticleName<br>ArticleValue
DefaultIdentification|DefaultIdentification field group|CaseActivity<br>KBArticle
## KBArticle (KB article) Entity 
A knowledge base document that contains technical information that may be relevant in customer support scenarios. 

Field | Description
---|---
ArticleScore | Data: Integer
Author | Lookup: Worker<br>Required
Description | Data: Text<br>Maximum length: 255
KBArticleId<br>Primary key | Number sequence: <br>Unique, Searchable
LinkToArticle | Data: WebsiteUrl
Synopsis | Data: MultilineText

###Field groups

Field group | Description | Fields
---|---|---
DefaultCreate|DefaultCreate field group|Description<br>Author<br>ArticleScore<br>LinkToArticle<br>Synopsis
DefaultList|DefaultList field group|KBArticleId<br>Description<br>Author<br>ArticleScore
DefaultCard|DefaultCard field group|KBArticleId<br>Author<br>ArticleScore
DefaultDetails|DefaultDetails field group|KBArticleId<br>Description<br>Author<br>ArticleScore<br>LinkToArticle<br>Synopsis
DefaultLookup|DefaultLookup field group|KBArticleId<br>Description<br>Author
DefaultReport|DefaultReport field group|KBArticleId<br>Description<br>Author<br>ArticleScore<br>LinkToArticle<br>Synopsis
DefaultIdentification|DefaultIdentification field group|KBArticleId<br>Description
