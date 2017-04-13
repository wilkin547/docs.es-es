---
title: "AcceptChanges y RejectChanges | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# AcceptChanges y RejectChanges
Después de comprobar la exactitud de los cambios realizados en una <xref:System.Data.DataTable>, se pueden aceptar con el método <xref:System.Data.DataRow.AcceptChanges%2A> de <xref:System.Data.DataRow>, <xref:System.Data.DataTable> o <xref:System.Data.DataSet>, que configurará los valores de fila **Current** de modo que sean los valores **Original** y establecerá la propiedad **RowState** en **Unchanged**.  Si se aceptan o se rechazan los cambios, se elimina la información de **RowError** y se establece la propiedad **HasErrors** en **false**.  Aceptar o rechazar cambios también puede afectar a la actualización de datos en el origen de datos.  Para obtener más información, consulta [Actualizar orígenes de datos con DataAdapters](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).  
  
 Si hay restricciones de clave externa en la **DataTable**, los cambios que se acepten o se rechacen con **AcceptChanges** y **RejectChanges** se propagan a las filas secundarias de la **DataRow** de acuerdo con la **ForeignKeyConstraint.AcceptRejectRule**.  Para obtener más información, consulta [Restricciones de DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 En el ejemplo siguiente se comprueba si hay filas con errores, se resuelven los errores que haya y se rechazan las filas en las que no se puede resolver el error.  Tenga en cuenta que, en los errores que se resuelven, el valor **RowError** se restablece en una cadena vacía, con lo que la propiedad **HasErrors** se establece en **false**.  Una vez que se han resuelto o rechazado todas las filas con errores, se llama a **AcceptChanges** para aceptar todos los cambios de toda la **DataTable**.  
  
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
  
## Vea también  
 <xref:System.Data.DataRow>   
 <xref:System.Data.DataSet>   
 <xref:System.Data.DataTable>   
 [Manipular datos en DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)