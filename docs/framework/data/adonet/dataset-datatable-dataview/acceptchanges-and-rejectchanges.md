---
description: 'Más información sobre: AcceptChanges y RejectChanges'
title: Objetos AcceptChange y RejectChange
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
ms.openlocfilehash: e21952063bf27f4f969669eb76b964fc7537b59a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725264"
---
# <a name="acceptchanges-and-rejectchanges"></a><span data-ttu-id="96ff7-103">Objetos AcceptChange y RejectChange</span><span class="sxs-lookup"><span data-stu-id="96ff7-103">AcceptChanges and RejectChanges</span></span>

<span data-ttu-id="96ff7-104">Después de comprobar la exactitud de los cambios realizados en los datos en un <xref:System.Data.DataTable> , puede aceptar los cambios mediante el <xref:System.Data.DataRow.AcceptChanges%2A> método de <xref:System.Data.DataRow> , <xref:System.Data.DataTable> o <xref:System.Data.DataSet> , que establecerá los valores de fila **actuales** para que sean los valores **originales** y establecerá la propiedad **RowState** en **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="96ff7-104">After verifying the accuracy of changes made to data in a <xref:System.Data.DataTable>, you can accept the changes using the <xref:System.Data.DataRow.AcceptChanges%2A> method of the <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, or <xref:System.Data.DataSet>, which will set the **Current** row values to be the **Original** values and will set the **RowState** property to **Unchanged**.</span></span> <span data-ttu-id="96ff7-105">Al aceptar o rechazar los cambios, se borra cualquier información de **RowError** y se establece la propiedad **hasErrors** en **false**.</span><span class="sxs-lookup"><span data-stu-id="96ff7-105">Accepting or rejecting changes clears out any **RowError** information and sets the **HasErrors** property to **false**.</span></span> <span data-ttu-id="96ff7-106">Aceptar o rechazar cambios también puede afectar a la actualización de datos en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="96ff7-106">Accepting or rejecting changes can also affect updating data in the data source.</span></span> <span data-ttu-id="96ff7-107">Para obtener más información, vea [Actualizar orígenes de datos con DataAdapters](../updating-data-sources-with-dataadapters.md).</span><span class="sxs-lookup"><span data-stu-id="96ff7-107">For more information, see [Updating Data Sources with DataAdapters](../updating-data-sources-with-dataadapters.md).</span></span>  
  
 <span data-ttu-id="96ff7-108">Si existen restricciones Foreign Key en **DataTable**, los cambios aceptados o rechazados mediante **AcceptChanges** y **RejectChanges** se propagan a las filas secundarias de **DataRow** según la **ForeignKeyConstraint. AcceptRejectRule**.</span><span class="sxs-lookup"><span data-stu-id="96ff7-108">If foreign key constraints exist on the **DataTable**, changes accepted or rejected using **AcceptChanges** and **RejectChanges** are propagated to child rows of the **DataRow** according to the **ForeignKeyConstraint.AcceptRejectRule**.</span></span> <span data-ttu-id="96ff7-109">Para obtener más información, vea [restricciones de DataTable](datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="96ff7-109">For more information, see [DataTable Constraints](datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="96ff7-110">En el ejemplo siguiente se comprueba si hay filas con errores, se resuelven los errores que haya y se rechazan las filas en las que no se puede resolver el error.</span><span class="sxs-lookup"><span data-stu-id="96ff7-110">The following example checks for rows with errors, resolves the errors where applicable, and rejects the rows where the error cannot be resolved.</span></span> <span data-ttu-id="96ff7-111">Tenga en cuenta que, en el caso de los errores resueltos, el valor de **RowError** se restablece en una cadena vacía, lo que hace que la propiedad **hasErrors** se establezca en **false**.</span><span class="sxs-lookup"><span data-stu-id="96ff7-111">Note that, for resolved errors, the **RowError** value is reset to an empty string, causing the **HasErrors** property to be set to **false**.</span></span> <span data-ttu-id="96ff7-112">Cuando todas las filas con errores se han resuelto o rechazado, se llama a **AcceptChanges** para aceptar todos los cambios de la **DataTable** completa.</span><span class="sxs-lookup"><span data-stu-id="96ff7-112">When all the rows with errors have been resolved or rejected, **AcceptChanges** is called to accept all changes for the entire **DataTable**.</span></span>  
  
```vb  
If workTable.HasErrors Then  
  Dim errRow As DataRow  
  
  For Each errRow in workTable.GetErrors()  
  
    If errRow.RowError = "Total cannot exceed 1000." Then  
      errRow("Total") = 1000  
      errRow.RowError = ""    ' Clear the error.  
    Else  
      errRow.RejectChanges()  
    End If  
  Next  
End If  
  
workTable.AcceptChanges()  
```  
  
```csharp  
if (workTable.HasErrors)  
{  
  
  foreach (DataRow errRow in workTable.GetErrors())  
  {  
    if (errRow.RowError == "Total cannot exceed 1000.")  
    {  
      errRow["Total"] = 1000;  
      errRow.RowError = "";    // Clear the error.  
    }  
    else  
      errRow.RejectChanges();  
  }  
}  
  
workTable.AcceptChanges();  
```  
  
## <a name="see-also"></a><span data-ttu-id="96ff7-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="96ff7-113">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="96ff7-114">Manipular datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="96ff7-114">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="96ff7-115">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="96ff7-115">ADO.NET Overview</span></span>](../ado-net-overview.md)
