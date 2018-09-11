---
title: Objetos AcceptChange y RejectChange
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
ms.openlocfilehash: 30b2c303b1823430c480f0706500f8f7e7053c4c
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2018
ms.locfileid: "44364285"
---
# <a name="acceptchanges-and-rejectchanges"></a><span data-ttu-id="29406-102">Objetos AcceptChange y RejectChange</span><span class="sxs-lookup"><span data-stu-id="29406-102">AcceptChanges and RejectChanges</span></span>
<span data-ttu-id="29406-103">Después de comprobar la exactitud de los cambios realizados a los datos en un <xref:System.Data.DataTable>, puede aceptar los cambios mediante el <xref:System.Data.DataRow.AcceptChanges%2A> método de la <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, o <xref:System.Data.DataSet>, que establecerá el **actual** fila los valores sean los **Original** valores y establecerá el **RowState** propiedad **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="29406-103">After verifying the accuracy of changes made to data in a <xref:System.Data.DataTable>, you can accept the changes using the <xref:System.Data.DataRow.AcceptChanges%2A> method of the <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, or <xref:System.Data.DataSet>, which will set the **Current** row values to be the **Original** values and will set the **RowState** property to **Unchanged**.</span></span> <span data-ttu-id="29406-104">Aceptar o rechazar cambios, se elimina **RowError** información y establece el **HasErrors** propiedad **false**.</span><span class="sxs-lookup"><span data-stu-id="29406-104">Accepting or rejecting changes clears out any **RowError** information and sets the **HasErrors** property to **false**.</span></span> <span data-ttu-id="29406-105">Aceptar o rechazar cambios también puede afectar a la actualización de datos en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="29406-105">Accepting or rejecting changes can also affect updating data in the data source.</span></span> <span data-ttu-id="29406-106">Para obtener más información, consulte [actualizar orígenes de datos con objetos DataAdapter](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).</span><span class="sxs-lookup"><span data-stu-id="29406-106">For more information, see [Updating Data Sources with DataAdapters](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).</span></span>  
  
 <span data-ttu-id="29406-107">Si existen restricciones de clave externa en el **DataTable**, los cambios se aceptan o rechazan mediante **AcceptChanges** y **RejectChanges** se propagan a las filas secundarias de la  **DataRow** según la **ForeignKeyConstraint.AcceptRejectRule**.</span><span class="sxs-lookup"><span data-stu-id="29406-107">If foreign key constraints exist on the **DataTable**, changes accepted or rejected using **AcceptChanges** and **RejectChanges** are propagated to child rows of the **DataRow** according to the **ForeignKeyConstraint.AcceptRejectRule**.</span></span> <span data-ttu-id="29406-108">Para obtener más información, consulte [restricciones de DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="29406-108">For more information, see [DataTable Constraints](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="29406-109">En el ejemplo siguiente se comprueba si hay filas con errores, se resuelven los errores que haya y se rechazan las filas en las que no se puede resolver el error.</span><span class="sxs-lookup"><span data-stu-id="29406-109">The following example checks for rows with errors, resolves the errors where applicable, and rejects the rows where the error cannot be resolved.</span></span> <span data-ttu-id="29406-110">Tenga en cuenta que, para resolver errores, el **RowError** valor se restablece en una cadena vacía, provocando la **HasErrors** propiedad se establece en **false**.</span><span class="sxs-lookup"><span data-stu-id="29406-110">Note that, for resolved errors, the **RowError** value is reset to an empty string, causing the **HasErrors** property to be set to **false**.</span></span> <span data-ttu-id="29406-111">Cuando todas las filas con errores se han resuelto o rechazado, **AcceptChanges** se llama para aceptar todos los cambios para toda la **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="29406-111">When all the rows with errors have been resolved or rejected, **AcceptChanges** is called to accept all changes for the entire **DataTable**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="29406-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="29406-112">See Also</span></span>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="29406-113">Manipulación de datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="29406-113">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="29406-114">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="29406-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
