---
title: Objetos AcceptChange y RejectChange
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
ms.openlocfilehash: c537fa808fc6ba4c740e71bfd70fe9cd1f3bd31a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785564"
---
# <a name="acceptchanges-and-rejectchanges"></a><span data-ttu-id="cf102-102">Objetos AcceptChange y RejectChange</span><span class="sxs-lookup"><span data-stu-id="cf102-102">AcceptChanges and RejectChanges</span></span>
<span data-ttu-id="cf102-103">Después de comprobar la exactitud de los cambios realizados en los datos <xref:System.Data.DataTable>en un, puede aceptar los cambios mediante <xref:System.Data.DataRow.AcceptChanges%2A> el método de <xref:System.Data.DataRow>, <xref:System.Data.DataTable>o <xref:System.Data.DataSet>, que establecerá los valores de fila **actuales** comoLos valores originales y establecerán la propiedad **RowState** en **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="cf102-103">After verifying the accuracy of changes made to data in a <xref:System.Data.DataTable>, you can accept the changes using the <xref:System.Data.DataRow.AcceptChanges%2A> method of the <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, or <xref:System.Data.DataSet>, which will set the **Current** row values to be the **Original** values and will set the **RowState** property to **Unchanged**.</span></span> <span data-ttu-id="cf102-104">Al aceptar o rechazar los cambios, se borra cualquier información de **RowError** y se establece la propiedad **hasErrors** en **false**.</span><span class="sxs-lookup"><span data-stu-id="cf102-104">Accepting or rejecting changes clears out any **RowError** information and sets the **HasErrors** property to **false**.</span></span> <span data-ttu-id="cf102-105">Aceptar o rechazar cambios también puede afectar a la actualización de datos en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="cf102-105">Accepting or rejecting changes can also affect updating data in the data source.</span></span> <span data-ttu-id="cf102-106">Para obtener más información, vea [Actualizar orígenes de datos con DataAdapters](../updating-data-sources-with-dataadapters.md).</span><span class="sxs-lookup"><span data-stu-id="cf102-106">For more information, see [Updating Data Sources with DataAdapters](../updating-data-sources-with-dataadapters.md).</span></span>  
  
 <span data-ttu-id="cf102-107">Si existen restricciones Foreign Key en **DataTable**, los cambios aceptados o rechazados mediante **AcceptChanges** y **RejectChanges** se propagan a las filas secundarias de **DataRow** según el  **ForeignKeyConstraint. AcceptRejectRule**.</span><span class="sxs-lookup"><span data-stu-id="cf102-107">If foreign key constraints exist on the **DataTable**, changes accepted or rejected using **AcceptChanges** and **RejectChanges** are propagated to child rows of the **DataRow** according to the **ForeignKeyConstraint.AcceptRejectRule**.</span></span> <span data-ttu-id="cf102-108">Para obtener más información, vea [restricciones de DataTable](datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="cf102-108">For more information, see [DataTable Constraints](datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="cf102-109">En el ejemplo siguiente se comprueba si hay filas con errores, se resuelven los errores que haya y se rechazan las filas en las que no se puede resolver el error.</span><span class="sxs-lookup"><span data-stu-id="cf102-109">The following example checks for rows with errors, resolves the errors where applicable, and rejects the rows where the error cannot be resolved.</span></span> <span data-ttu-id="cf102-110">Tenga en cuenta que, en el caso de los errores resueltos, el valor de **RowError** se restablece en una cadena vacía, lo que hace que la propiedad **hasErrors** se establezca en **false**.</span><span class="sxs-lookup"><span data-stu-id="cf102-110">Note that, for resolved errors, the **RowError** value is reset to an empty string, causing the **HasErrors** property to be set to **false**.</span></span> <span data-ttu-id="cf102-111">Cuando todas las filas con errores se han resuelto o rechazado, se llama a **AcceptChanges** para aceptar todos los cambios de la **DataTable**completa.</span><span class="sxs-lookup"><span data-stu-id="cf102-111">When all the rows with errors have been resolved or rejected, **AcceptChanges** is called to accept all changes for the entire **DataTable**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cf102-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf102-112">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="cf102-113">Manipulación de datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="cf102-113">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="cf102-114">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="cf102-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
