---
title: Objetos DataRow y DataRowView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8f5eec26-b809-4aca-8778-7e202356d856
ms.openlocfilehash: 5bd7ebefc03dbe6b44a199ba3123414e7b282c90
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44135229"
---
# <a name="datarows-and-datarowviews"></a><span data-ttu-id="12076-102">Objetos DataRow y DataRowView</span><span class="sxs-lookup"><span data-stu-id="12076-102">DataRows and DataRowViews</span></span>
<span data-ttu-id="12076-103">Un <xref:System.Data.DataView> expone una colección enumerable de objetos <xref:System.Data.DataRowView>.</span><span class="sxs-lookup"><span data-stu-id="12076-103">A <xref:System.Data.DataView> exposes an enumerable collection of <xref:System.Data.DataRowView> objects.</span></span> <span data-ttu-id="12076-104">El **DataRowView** objetos exponen valores como matrices de objetos que se indizan por el nombre o la referencia ordinal de la columna en la tabla subyacente.</span><span class="sxs-lookup"><span data-stu-id="12076-104">The **DataRowView** objects expose values as object arrays that are indexed by either the name or the ordinal reference of the column in the underlying table.</span></span> <span data-ttu-id="12076-105">Puede tener acceso a la <xref:System.Data.DataRow> que se expone mediante el **DataRowView** utilizando el <xref:System.Data.DataRowView.Row%2A> propiedad de la **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="12076-105">You can access the <xref:System.Data.DataRow> that is exposed by the **DataRowView** by using the <xref:System.Data.DataRowView.Row%2A> property of the **DataRowView**.</span></span>  
  
 <span data-ttu-id="12076-106">Cuando se ven valores mediante el uso de un **DataRowView**, el <xref:System.Data.DataView.RowStateFilter%2A> propiedad de la **DataView** determina qué versión de fila de subyacente **DataRow** se expone.</span><span class="sxs-lookup"><span data-stu-id="12076-106">When you view values by using a **DataRowView**, the <xref:System.Data.DataView.RowStateFilter%2A> property of the **DataView** determines which row version of the underlying **DataRow** is exposed.</span></span> <span data-ttu-id="12076-107">Para obtener información sobre el acceso a diferentes versiones de fila mediante una **DataRow**, consulte [Estados de fila y las versiones de fila](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="12076-107">For information about accessing different row versions using a **DataRow**, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="12076-108">El siguiente ejemplo de código muestra todos los valores actuales y originales de una tabla.</span><span class="sxs-lookup"><span data-stu-id="12076-108">The following code example displays all the current and original values in a table.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="12076-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="12076-109">See Also</span></span>  
 <xref:System.Data.DataRowVersion>  
 <xref:System.Data.DataViewRowState>  
 <xref:System.Data.DataView>  
 <xref:System.Data.DataRowView>  
 [<span data-ttu-id="12076-110">Objetos DataView</span><span class="sxs-lookup"><span data-stu-id="12076-110">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="12076-111">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="12076-111">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
