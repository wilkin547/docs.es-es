---
title: Objetos DataRow y DataRowView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8f5eec26-b809-4aca-8778-7e202356d856
ms.openlocfilehash: fba160cb1f6948aa57221ff42ad9b0d673b88749
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="datarows-and-datarowviews"></a>Objetos DataRow y DataRowView
Un <xref:System.Data.DataView> expone una colección enumerable de objetos <xref:System.Data.DataRowView>. El **DataRowView** objetos exponen valores como matrices de objetos indizadas por el nombre o la referencia ordinal de la columna en la tabla subyacente. Puede tener acceso a la <xref:System.Data.DataRow> que se expone mediante el **DataRowView** mediante el uso de la <xref:System.Data.DataRowView.Row%2A> propiedad de la **DataRowView**.  
  
 Cuando se ven valores mediante el uso de un **DataRowView**, <xref:System.Data.DataView.RowStateFilter%2A> propiedad de la **DataView** determina qué versión de fila de subyacente **DataRow** se expone. Para obtener información acerca del acceso a diferentes versiones de fila mediante una **DataRow**, consulte [Estados de fila y versiones de fila](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
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
  
## <a name="see-also"></a>Vea también  
 <xref:System.Data.DataRowVersion>  
 <xref:System.Data.DataViewRowState>  
 <xref:System.Data.DataView>  
 <xref:System.Data.DataRowView>  
 [Objetos DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
