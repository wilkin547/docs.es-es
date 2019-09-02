---
title: Objetos AcceptChange y RejectChange
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
ms.openlocfilehash: a8589b157bc2579a03d856b73802abc9a4b42855
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204080"
---
# <a name="acceptchanges-and-rejectchanges"></a>Objetos AcceptChange y RejectChange
Después de comprobar la exactitud de los cambios realizados en los datos <xref:System.Data.DataTable>en un, puede aceptar los cambios mediante <xref:System.Data.DataRow.AcceptChanges%2A> el método de <xref:System.Data.DataRow>, <xref:System.Data.DataTable>o <xref:System.Data.DataSet>, que establecerá los valores de fila **actuales** comoLos valores originales y establecerán la propiedad **RowState** en Unchanged. Al aceptar o rechazar los cambios, se borra cualquier información de **RowError** y se establece la propiedad **hasErrors** en **false**. Aceptar o rechazar cambios también puede afectar a la actualización de datos en el origen de datos. Para obtener más información, vea [Actualizar orígenes de datos con DataAdapters](../updating-data-sources-with-dataadapters.md).  
  
 Si existen restricciones Foreign Key en **DataTable**, los cambios aceptados o rechazados mediante **AcceptChanges** y **RejectChanges** se propagan a las filas secundarias de **DataRow** según el  **ForeignKeyConstraint. AcceptRejectRule**. Para obtener más información, vea [restricciones de DataTable](datatable-constraints.md).  
  
 En el ejemplo siguiente se comprueba si hay filas con errores, se resuelven los errores que haya y se rechazan las filas en las que no se puede resolver el error. Tenga en cuenta que, en el caso de los errores resueltos, el valor de **RowError** se restablece en una cadena vacía, lo que hace que la propiedad **hasErrors** se establezca en **false**. Cuando todas las filas con errores se han resuelto o rechazado, se llama a **AcceptChanges** para aceptar todos los cambios de la **DataTable**completa.  
  
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

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [Manipulación de datos en un objeto DataTable](manipulating-data-in-a-datatable.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
