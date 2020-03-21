---
title: Objetos DataRow y DataRowView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8f5eec26-b809-4aca-8778-7e202356d856
ms.openlocfilehash: 14e7e1ccb051410c351e49afee9f2d6809264833
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151304"
---
# <a name="datarows-and-datarowviews"></a>Objetos DataRow y DataRowView
Un <xref:System.Data.DataView> expone una colección enumerable de objetos <xref:System.Data.DataRowView>. El **DataRowView** objetos exponen valores como matrices de objetos que se indizan por el nombre o la referencia ordinal de la columna en la tabla subyacente. Puede tener <xref:System.Data.DataRow> acceso a la que expone El <xref:System.Data.DataRowView.Row%2A> **DataRowView** mediante la propiedad de la **DataRowView**.  
  
 Cuando se ven valores mediante un <xref:System.Data.DataView.RowStateFilter%2A> **DataRowView**, la propiedad de la **DataView** determina qué versión de fila de la **subyacente DataRow** se expone. Para obtener información sobre cómo obtener acceso a diferentes versiones de fila mediante **DataRow**, vea Estados de fila [y versiones](row-states-and-row-versions.md)de fila .  
  
 El siguiente ejemplo de código muestra todos los valores actuales y originales de una tabla.  
  
```vb  
Dim catView As DataView = New DataView(catDS.Tables("Categories"))  
Console.WriteLine("Current Values:")  
WriteView(catView)  
Console.WriteLine("Original Values:")  
catView.RowStateFilter = DataViewRowState.ModifiedOriginal  
WriteView(catView)
  
Public Shared Sub WriteView(thisDataView As DataView)  
  Dim rowView As DataRowView  
  Dim i As Integer  
  
  For Each rowView In thisDataView  
    For i = 0 To thisDataView.Table.Columns.Count - 1  
      Console.Write(rowView(i) & vbTab)  
    Next  
    Console.WriteLine()  
  Next  
End Sub  
```  
  
```csharp  
DataView catView = new DataView(catDS.Tables["Categories"]);  
Console.WriteLine("Current Values:");  
WriteView(catView);  
Console.WriteLine("Original Values:");  
catView.RowStateFilter = DataViewRowState.ModifiedOriginal;  
WriteView(catView);  
  
public static void WriteView(DataView thisDataView)  
{  
  foreach (DataRowView rowView in thisDataView)  
  {  
    for (int i = 0; i < thisDataView.Table.Columns.Count; i++)  
      Console.Write(rowView[i] + "\t");  
    Console.WriteLine();  
  }  
}  
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Data.DataRowVersion>
- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [Objetos DataView](dataviews.md)
- [Información general de ADO.NET](../ado-net-overview.md)
