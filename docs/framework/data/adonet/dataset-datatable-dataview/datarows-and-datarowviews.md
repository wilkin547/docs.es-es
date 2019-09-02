---
title: Objetos DataRow y DataRowView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8f5eec26-b809-4aca-8778-7e202356d856
ms.openlocfilehash: 8a98dc44eda9ebda09235193c58bd831fc52d04d
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205092"
---
# <a name="datarows-and-datarowviews"></a>Objetos DataRow y DataRowView
Un <xref:System.Data.DataView> expone una colección enumerable de objetos <xref:System.Data.DataRowView>. Los objetos **DataRowView** exponen valores como matrices de objetos que se indizan mediante el nombre o la referencia ordinal de la columna en la tabla subyacente. Puede tener acceso al <xref:System.Data.DataRow> que expone la **DataRowView** mediante la <xref:System.Data.DataRowView.Row%2A> propiedad de la **DataRowView**.  
  
 Cuando se ven valores mediante una **DataRowView**, la propiedad <xref:System.Data.DataView.RowStateFilter%2A> de **DataView** determina la versión de fila de la **DataRow** subyacente que se expone. Para obtener información sobre cómo obtener acceso a diferentes versiones de fila mediante **DataRow**, vea [Estados de fila y versiones de fila](row-states-and-row-versions.md).  
  
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

- <xref:System.Data.DataRowVersion>
- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [Objetos DataView](dataviews.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
