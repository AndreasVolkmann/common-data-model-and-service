<properties
	pageTitle="Column control in PowerApps"
	description="This topic provides information about the Column control in Microsoft PowerApps."
	services="powerapps"
	documentationCenter="na"
	authors="jasongre"
	manager="kfend"
	editor=""
	tags=""/>

<tags
   ms.service="powerapps"
   ms.devlang="na"
   ms.topic="article"
   ms.tgt_pltfrm="na"
   ms.workload="na"
   ms.date="05/30/2017"
   ms.author="kfend"/>
   
# Column control in PowerApps (in CDS content)

Provides the display experience for a single field in a [**Data table**](https://powerapps.microsoft.com/en-us/tutorials/control-data-table/) control.

## Description

The [**Data table**](https://powerapps.microsoft.com/en-us/tutorials/control-data-table/) control shows a dataset in a tabular format, and each column in that tabular format is represented by a **Column** control. The **Column** control provides properties that the app maker can use to customize the appearance and behavior of the column.

## Capabilities

### Now available
- Change the width of a **Column** control.
- Change the text for a **Column** control.
- Navigate by clicking or tapping the value in a **Column** control.

### Not yet available
- Customize the styling of a **Column** control.

### Known issues
- The **Visible** property doesn't work yet.

## Properties

+ **DisplayName** – The text that is shown in the header for the column.

    > [!NOTE]
    > This property will soon be renamed **HeaderText**.

+ **IsHyperlink** – A value that indicates whether the data in the column should be underlined to indicate that it's a hyperlink.
+ [**Width**](https://powerapps.microsoft.com/en-us/tutorials/properties-size-location/ "Width") – The distance between the **Column** control’s left and right edges.

## Examples
### Resize a column

1. Create a blank tablet app.
2. On the **Insert** tab, click or tap **Data table**, and then resize the **Data table** control so that it covers the whole screen.
3. In the right pane, click or tap the data source icon to the right of **No data source selected**, and then click or tap **Add a data source**.
5. In the list of connections, click or tap the connection for your Common Data Service database. 
6. In the list of entities, click or tap **Account**, and then click or tap **Connect**. The **Data table** control is initialized and shows a set of default fields. 
7. Click or tap the **Total amount** column.

	![Column control selected](Media/preResizeColumn.png "Column control selected")

8. Drag the adorner on the right side to resize the field.

	![Column control resized](Media/postResizeColumn.png "Column control resized")
