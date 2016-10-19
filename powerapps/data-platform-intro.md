<properties
	pageTitle="Understand entities | Microsoft Common Data Model"
	description="Introduction to entities, fields, relationships, and databases."
	services="powerapps"
	documentationCenter="na"
	authors="clwesene"
	manager="RobinARH"
	editor=""
	tags=""/>

<tags
   ms.service="powerapps"
   ms.devlang="na"
   ms.topic="article"
   ms.tgt_pltfrm="na"
   ms.workload="na"
   ms.date="10/19/2016"
   ms.author="robinr"/>

# Understand entities in the Common Data Service

[AZURE.VIDEO nb:cid:UUID:609a7777-309f-4b6b-87eb-274dd33cac94]

The Common Data Service allows you to store and manage data within a set of standard and custom entities securely. An entity is a set of fields used to store data similarly to a table within a database. Once your data is stored you can use PowerApps to build rich applications using your data :

- Import data into standard or custom entities.
- Create custom entities to support your scenario and application.
- Add custom fields to standard entities where additional inforatmion is needed.
- Incorporate standard and custom entities into an app that you're developing, as easily as with data in other sources.
- Leverage the productivity add-ins to access your data from Excel and Outlook.
- Secure your data within your orginization using role-based security against standard and custom entities.
- Include picklists of predefined data like Country, Salutation, and Currency, etc.
- Provide global support for your data and applications by leveraging translation of entity and field names.

Each entity contains a set of records that users can create, read, update, and delete. You can create relationships between entities so that you can look up information in one entity based on a record in another entity. For example, you could create a custom entity to track events which a customer had attended. By adding the Customer to your custom entity as a lookup field, you establish a relationship between the two entities which can be leveraged in your app and in reporting.

## Why use entities?

Entities within the Common Data Model, both standard and custom, allow a secure and cloud based storage option for your data. Entities allow you to create a business-focused definition of your data for use within your apps. If you're not sure whether entities are your best option, consider these benefits:

- Easy to manage: Both the metadata and data are stored in the cloud. You don't need to worry about the details of how they're stored.
- Easy to share: You can easily share data with your colleagues because PowerApps manages the permissions.
- Easy to Secure: Data is stored securely so that users can see it only if you grant them access. Role-based security allows you to contorl access to entities for different users within your organization.
- Rich metadata: Data types and relationships are leveraged directly within PowerApps. For example, defining a field type URL will present your data as a hyperlink within your app.
- Productivity tools: entities are available within the add-ins for Microsoft Excel and Outlook to increase productivty, and ensure your data is accessible.
- Include picklists from a rich set of standard picklists to provide quick drop downs within your entities and apps.

## Standard and custom entities
When you develop an app, you can use standard entities, custom entities, or both. If a standard entity can serve a particular purpose in your app, you should use it rather than developing a custom entity that does the same thing. If a standard entity would serve a purpose with a few changes, you can add fields to suit your needs. 

- The Common Data Service provides standard entities by default. These are designed, in accordance with best practices, to capture the most common concepts for an organization, such as Contacts, Accounts, and Products. For the full list, see [Standard entities](data-platform-intro.md#standard-entities).
- You can extend the functionality of standard entities by creating one or more custom entities to store information that's unique to your organization. For more information, see [how to create a custom entity](data-platform-create-entity.md).

>**Note:** Whenever possible, use standard entities (with custom fields added if required). This will ensure you can benefit from new features or apps which leverage these entities in the future.

## Fields
Each field has a name, a display name, a data type, and some simple validation. Data types include, for example, **text**, **date** or **number**, and validation ensures that required fields contain data and records are unique if the entity requires them to be. Every field falls into one of three categories: system fields, standard fields, or custom fields.

### System fields
All entities, whether standard or custom, are created with a set of read-only fields that you can't change, delete, or set to a value. For more information, see [System and record title fields](data-platform-create-entity.md#system-and-record-title-fields). These are the most important system fields:

- **Created Record Date**: The date and time when a record was created.
- **Created By**: The user who created the record.
- **Modified Record Date**: The date and time when a record was modified most recently.
- **Last Modified By**: The user who modified the record most recently.

### Standard fields
Each standard entity contains a set of default fields that you can't change or delete. For a list of the entities and their fields, and a list of the picklists, see [Microsoft Common Data Model, Entities Reference](http://download.microsoft.com/download/8/9/5/8956ED58-A9B0-40DF-8CB0-BC13AD8DB6E2/CDMEntityReference.docx).

### Custom fields ###
You can create custom fields in either a standard entity or a custom entity. You must specify the name, the display name, and the data type of each custom field. PowerApps supports these data types:

- **Boolean**: True or false.
- **Currency**: A numeric value that represents money.
- **DateTime**: A date and time.
- **Date**: A date.
- **Email**: A text value that represents an email address.
- **Enumeration**: One value from a list of values.
- **Image**: An image.
- **Integer**: A positive or negative value.
- **Lookup**: A lookup field into another entity's title field.
- **Multi line text**: Multiple lines of text.
- **Number**: A number.
- **Number Sequence**: A sequence number that's read-only and generated automatically. Usually used as the record's unique ID.
- **Phone**: A text value that represents a phone number.
- **Text**: Text of length up to 128 characters.
- **URL**: A text value that represents a URL.

For more information, see [Manage fields in an entity](data-platform-manage-fields.md).

## Lookup relationships ##
You can navigate between records in entities if they have a relationship that's defined as a field of the **Lookup** data type. To create a lookup relationship, add a field of data type **Lookup** in one entity, and point to the entity in which you want to look up information. For more information, see [Entity relationships via lookup field](data-platform-entity-lookup.md).

## Standard entities
For a list of the entities and their fields, and a list of the enumerations, see [Microsoft Common Data Model, Entities Reference](http://download.microsoft.com/download/8/9/5/8956ED58-A9B0-40DF-8CB0-BC13AD8DB6E2/CDMEntityReference.docx).

Functional Group | Description | Entities
--- | --- | ---
Foundation | The Foundation entities contain information that is relevant to nearly every other entity group. This group contains entities such as Address and Currency. | Cost Center<br> Country Region<br> Currency<br> Postal Codes<br> Product<br> Product Category<br> State list<br> Unit Conversion<br> Unit
People, Organizations, and Groups | These entities encompass a rich set of people and organizations that you might interact with, including employees, contractors, donors, volunteers, fans, alumni, and families. | Alumnus<br> Business Unit<br> Company<br> Constituent<br> Contractor<br> Donor<br> Employee<br> Family<br> Family Member<br> Fan<br> Household<br> Household Member<br> Member<br> Team<br> Team Member<br> Tenant<br> User<br> Volunteer<br>
Purchasing | The Purchasing entities let you create purchasing solutions.  | Purchase Order<br> Purchase Order Charge<br> Purchase Order Line<br> Purchase Order Line Charge<br> Purchase Order Line Receipt<br> Purchase Order Line Tax<br> Purchase Order Tax<br> Supplier<br> Supplier Invoice<br> Supplier Invoice Charge<br> Supplier Invoice Line<br> Supplier Invoice Line Charge<br> Supplier Invoice Line Tax<br> Supplier Invoice Tax
Sales | The Sales entities let you create end-to-end sales solutions, from tracking leads and opportunities, to following through with contacts, to accepting and delivering orders, to sending invoices. | Contact<br> Customer<br> Lead<br> Opportunity<br> OpportunityPartyRole<br> Partner<br> SalesInvoice<br> Sales Invoice Charge<br> Sales Invoice Line<br> Sales Invoice Line Charge<br> Sales Invoice Line Tax<br> Sales Invoice Tax<br> Sales Order<br> Sales Order Charge<br> Sales Order Line<br> Sales Order Line Charge<br> Sales Order Line Shipment<br> Sales Order Line Tax<br> Sales Order Tax
Case Management | The Case Management entities manage issues from your customers, including tracking, escalation, and documentation. | Case<br> Case Activity<br> Case Activity KB Article<br> Case Worker Assignment<br> KB Article

//TODO - Review and update against what will ship

## Get started ##
Try it out by creating an app using a standard entity or [create a custom entity](data-platform-create-entity.md) and then [creating an app that uses that entity](data-platform-create-app.md).

//TODO - Add Link for Standard entity app - Template?
