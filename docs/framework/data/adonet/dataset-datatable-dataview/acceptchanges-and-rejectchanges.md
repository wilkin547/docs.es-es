---
title: Objetos AcceptChange y RejectChange
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
ms.openlocfilehash: 30b2c303b1823430c480f0706500f8f7e7053c4c
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2018
ms.locfileid: "45595742"
---
# <a name="acceptchanges-and-rejectchanges"></a>Objetos AcceptChange y RejectChange
Después de comprobar la exactitud de los cambios realizados a los datos en un <xref:System.Data.DataTable>, puede aceptar los cambios mediante el <xref:System.Data.DataRow.AcceptChanges%2A> método de la <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, o <xref:System.Data.DataSet>, que establecerá el **actual** fila los valores sean los **Original** valores y establecerá el **RowState** propiedad **Unchanged**. Aceptar o rechazar cambios, se elimina **RowError** información y establece el **HasErrors** propiedad **false**. Aceptar o rechazar cambios también puede afectar a la actualización de datos en el origen de datos. Para obtener más información, consulte [actualizar orígenes de datos con objetos DataAdapter](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).  
  
 Si existen restricciones de clave externa en el **DataTable**, los cambios se aceptan o rechazan mediante **AcceptChanges** y **RejectChanges** se propagan a las filas secundarias de la  **DataRow** según la **ForeignKeyConstraint.AcceptRejectRule**. Para obtener más información, consulte [restricciones de DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 En el ejemplo siguiente se comprueba si hay filas con errores, se resuelven los errores que haya y se rechazan las filas en las que no se puede resolver el error. Tenga en cuenta que, para resolver errores, el **RowError** valor se restablece en una cadena vacía, provocando la **HasErrors** propiedad se establece en **false**. Cuando todas las filas con errores se han resuelto o rechazado, **AcceptChanges** se llama para aceptar todos los cambios para toda la **DataTable**.  
  
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
  
## <a name="see-also"></a>Vea también  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [Manipulación de datos en un objeto DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
