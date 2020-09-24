---
title: Objetos DataRow y DataRowView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8f5eec26-b809-4aca-8778-7e202356d856
ms.openlocfilehash: bce90c1d310178e66da7c758c6df2cd357199c8b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153292"
---
# <a name="datarows-and-datarowviews"></a><span data-ttu-id="65be6-102">Objetos DataRow y DataRowView</span><span class="sxs-lookup"><span data-stu-id="65be6-102">DataRows and DataRowViews</span></span>

<span data-ttu-id="65be6-103">Un <xref:System.Data.DataView> expone una colección enumerable de objetos <xref:System.Data.DataRowView>.</span><span class="sxs-lookup"><span data-stu-id="65be6-103">A <xref:System.Data.DataView> exposes an enumerable collection of <xref:System.Data.DataRowView> objects.</span></span> <span data-ttu-id="65be6-104">Los objetos **DataRowView** exponen valores como matrices de objetos que se indizan mediante el nombre o la referencia ordinal de la columna en la tabla subyacente.</span><span class="sxs-lookup"><span data-stu-id="65be6-104">The **DataRowView** objects expose values as object arrays that are indexed by either the name or the ordinal reference of the column in the underlying table.</span></span> <span data-ttu-id="65be6-105">Puede tener acceso al <xref:System.Data.DataRow> que expone la **DataRowView** mediante la <xref:System.Data.DataRowView.Row%2A> propiedad de la **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="65be6-105">You can access the <xref:System.Data.DataRow> that is exposed by the **DataRowView** by using the <xref:System.Data.DataRowView.Row%2A> property of the **DataRowView**.</span></span>  
  
 <span data-ttu-id="65be6-106">Cuando se ven valores mediante una **DataRowView**, la <xref:System.Data.DataView.RowStateFilter%2A> propiedad de **DataView** determina la versión de fila de la **DataRow** subyacente que se expone.</span><span class="sxs-lookup"><span data-stu-id="65be6-106">When you view values by using a **DataRowView**, the <xref:System.Data.DataView.RowStateFilter%2A> property of the **DataView** determines which row version of the underlying **DataRow** is exposed.</span></span> <span data-ttu-id="65be6-107">Para obtener información sobre cómo obtener acceso a diferentes versiones de fila mediante **DataRow**, vea [Estados de fila y versiones de fila](row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="65be6-107">For information about accessing different row versions using a **DataRow**, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="65be6-108">El siguiente ejemplo de código muestra todos los valores actuales y originales de una tabla.</span><span class="sxs-lookup"><span data-stu-id="65be6-108">The following code example displays all the current and original values in a table.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="65be6-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="65be6-109">See also</span></span>

- <xref:System.Data.DataRowVersion>
- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [<span data-ttu-id="65be6-110">Objetos DataView</span><span class="sxs-lookup"><span data-stu-id="65be6-110">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="65be6-111">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="65be6-111">ADO.NET Overview</span></span>](../ado-net-overview.md)
