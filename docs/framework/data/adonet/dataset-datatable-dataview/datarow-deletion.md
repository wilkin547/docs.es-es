---
title: Eliminación de DataRow
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
ms.openlocfilehash: 128c41e1906b17e7f42458e8a5f1b3d3ec9cc449
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="datarow-deletion"></a>Eliminación de DataRow
Hay dos métodos que puede usar para eliminar un <xref:System.Data.DataRow> objeto desde un <xref:System.Data.DataTable> objeto: el **quitar** método de la <xref:System.Data.DataRowCollection> objeto y el <xref:System.Data.DataRow.Delete%2A> método de la **DataRow**objeto. Mientras que la <xref:System.Data.DataRowCollection.Remove%2A> método elimina un **DataRow** desde el **DataRowCollection**, el <xref:System.Data.DataRow.Delete%2A> método solo marca la fila para su eliminación. La eliminación propiamente dicha se produce cuando la aplicación llama a la **AcceptChanges** método. Con <xref:System.Data.DataRow.Delete%2A>, se puede comprobar mediante programa qué filas están marcadas para eliminación antes de quitarlas realmente. Cuando una fila está marcada para eliminación, la propiedad <xref:System.Data.DataRow.RowState%2A> se establece en <xref:System.Data.DataRow.Delete%2A>.  
  
 No se debe llamar a <xref:System.Data.DataRow.Delete%2A> ni a <xref:System.Data.DataRowCollection.Remove%2A> en un bucle foreach durante una iteración a través de un objeto <xref:System.Data.DataRowCollection> . Ni <xref:System.Data.DataRow.Delete%2A> ni <xref:System.Data.DataRowCollection.Remove%2A> modifican el estado de la colección.  
  
 Cuando se usa un <xref:System.Data.DataSet> o **DataTable** junto con un **DataAdapter** y un origen de datos relacional, utilice la **eliminar** método de la  **DataRow** para quitar la fila. El **eliminar** método marca la fila como **Deleted** en el **conjunto de datos** o **DataTable** pero no se quita. En su lugar, cuando la **DataAdapter** encuentra una fila marcada como **Deleted**, ejecuta su **DeleteCommand** método para eliminar la fila en el origen de datos. La fila puede, a continuación, puede quitar permanentemente usando el **AcceptChanges** método. Si usa **quitar** para eliminar la fila, la fila se quita por completo de la tabla, pero la **DataAdapter** no eliminará la fila del origen de datos.  
  
 El **quitar** método de la **DataRowCollection** toma una **DataRow** como argumento y la quita de la colección, como se muestra en el ejemplo siguiente.  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 En cambio, en el ejemplo siguiente se muestra cómo llamar a la **eliminar** método en un **DataRow** para cambiar su **RowState** a **Deleted** .  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 Si una fila está marcada para su eliminación y se llama el **AcceptChanges** método de la **DataTable** objeto, la fila se quita de la **DataTable**. En cambio, si se llama a **RejectChanges**, **RowState** de la fila vuelve al que tenía antes de que se marcara como **Deleted**.  
  
> [!NOTE]
>  Si el **RowState** de un **DataRow** es **Added**, lo que significa que se acaba de agregar a la tabla y, a continuación, se marca como **Deleted**, es Quita de la tabla.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataRowCollection>  
 <xref:System.Data.DataTable>  
 [Manipulación de datos en un objeto DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
