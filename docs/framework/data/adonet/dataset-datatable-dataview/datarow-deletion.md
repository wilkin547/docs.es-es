---
title: "Eliminar DataRow | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Eliminar DataRow
Existen dos métodos para eliminar un objeto <xref:System.Data.DataRow> de un objeto <xref:System.Data.DataTable>: el método **Remove** del objeto <xref:System.Data.DataRowCollection> y el método <xref:System.Data.DataRow.Delete%2A> del objeto **DataRow**.  Aunque el método <xref:System.Data.DataRowCollection.Remove%2A> elimine un objeto **DataRow** de **DataRowCollection**, el método <xref:System.Data.DataRow.Delete%2A> solo marca la fila que se deben eliminar.  La eliminación propiamente dicha se produce cuando la aplicación llama al método **AcceptChanges**.  Con <xref:System.Data.DataRow.Delete%2A>, se puede comprobar mediante programa qué filas están marcadas para eliminación antes de quitarlas realmente.  Cuando una fila está marcada para eliminación, la propiedad <xref:System.Data.DataRow.RowState%2A> se establece en <xref:System.Data.DataRow.Delete%2A>.  
  
 No se debe llamar a <xref:System.Data.DataRow.Delete%2A> ni a <xref:System.Data.DataRowCollection.Remove%2A> en un bucle foreach durante una iteración a través de un objeto <xref:System.Data.DataRowCollection> .  Ni <xref:System.Data.DataRow.Delete%2A> ni <xref:System.Data.DataRowCollection.Remove%2A> modifican el estado de la colección.  
  
 Si utiliza un <xref:System.Data.DataSet> o una **DataTable** en combinación con un **DataAdapter** y un origen de datos relacional, utilice el método **Delete** de la **DataRow** para quitar la fila.  El método **Delete** marca la fila como **Deleted** en **DataSet** o **DataTable** pero no la quita.  En su lugar, cuando el **DataAdapter** encuentra una fila marcada como **Deleted**, ejecuta el método **DeleteCommand** para eliminar la fila en el origen de datos.  A continuación se puede quitar la fila permanentemente utilizando el método **AcceptChanges**.  Si utiliza **Remove** para quitar la fila, ésta desaparecerá por completo de la tabla, pero el **DataAdapter** no eliminará la fila del origen de datos.  
  
 El método **Remove** de la **DataRowCollection** toma una **DataRow** como argumento y la quita de la colección, como se muestra en el ejemplo siguiente.  
  
```vb  
workTable.Rows.Remove(workRow)  
  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 Por el contrario, en el siguiente ejemplo se muestra cómo se llama al método **Delete** en una **DataRow** para cambiar el **RowState** a **Deleted**.  
  
```vb  
workRow.Delete  
  
```  
  
```csharp  
workRow.Delete();  
```  
  
 Si una fila está marcada para eliminación y se llama al método **AcceptChanges** del objeto **DataTable**, la fila se quita de la **DataTable**.  Por el contrario, si se llama a **RejectChanges**, el **RowState** de la fila vuelve a ser el que era antes de que se marcara como **Deleted**.  
  
> [!NOTE]
>  Si el **RowState** de una **DataRow** se **Added**, lo que quiere decir que se acaba de agregar a la tabla y, a continuación, se marca como **Deleted**, se quita de la tabla.  
  
## Vea también  
 <xref:System.Data.DataRow>   
 <xref:System.Data.DataRowCollection>   
 <xref:System.Data.DataTable>   
 [Manipular datos en DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)