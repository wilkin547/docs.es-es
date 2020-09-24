---
title: Eliminación de DataRow
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
ms.openlocfilehash: 2092d7319a398bbdeaef764d677818f78ddf9de9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153357"
---
# <a name="datarow-deletion"></a>Eliminación de DataRow

Hay dos métodos que puede usar para eliminar un <xref:System.Data.DataRow> objeto de un <xref:System.Data.DataTable> objeto: el método **Remove** del <xref:System.Data.DataRowCollection> objeto y el <xref:System.Data.DataRow.Delete%2A> método del objeto **DataRow** . Mientras que el <xref:System.Data.DataRowCollection.Remove%2A> método elimina una **DataRow** de la **DataRowCollection**, el <xref:System.Data.DataRow.Delete%2A> método solo marca la fila para su eliminación. La eliminación real se produce cuando la aplicación llama al método **AcceptChanges** . Con <xref:System.Data.DataRow.Delete%2A>, se puede comprobar mediante programa qué filas están marcadas para eliminación antes de quitarlas realmente. Cuando una fila está marcada para eliminación, la propiedad <xref:System.Data.DataRow.RowState%2A> se establece en <xref:System.Data.DataRow.Delete%2A>.  
  
 No se debe llamar a <xref:System.Data.DataRow.Delete%2A> ni a <xref:System.Data.DataRowCollection.Remove%2A> en un bucle foreach durante una iteración a través de un objeto <xref:System.Data.DataRowCollection> . Ni <xref:System.Data.DataRow.Delete%2A> ni <xref:System.Data.DataRowCollection.Remove%2A> modifican el estado de la colección.  
  
 Al utilizar un <xref:System.Data.DataSet> **objeto o DataTable** junto con un **DataAdapter** y un origen de datos relacional, utilice el método **Delete** de **DataRow** para quitar la fila. El método **Delete** marca la fila como **eliminada** en el **DataSet** o **DataTable** , pero no la quita. En su lugar, cuando el **DataAdapter** encuentra una fila marcada como **Deleted**, ejecuta su método **DeleteCommand** para eliminar la fila en el origen de datos. La fila se puede quitar de forma permanente mediante el método **AcceptChanges** . Si utiliza **Remove** para eliminar la fila, la fila se quita completamente de la tabla, pero el **DataAdapter** no eliminará la fila del origen de datos.  
  
 El método **Remove** de la **DataRowCollection** toma un **DataRow** como argumento y lo quita de la colección, tal y como se muestra en el ejemplo siguiente.  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 En cambio, en el ejemplo siguiente se muestra cómo llamar al método **Delete** en una **DataRow** para cambiar su **RowState** a **Deleted**.  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 Si una fila está marcada para su eliminación y se llama al método **AcceptChanges** del objeto **DataTable** , la fila se quita de la **DataTable**. Por el contrario, si se llama a **RejectChanges**, el **RowState** de la fila se revierte a lo que era antes de marcarse como **eliminado**.  
  
> [!NOTE]
> Si se **agrega**el **RowState** de una **DataRow** , lo que significa que se acaba de agregar a la tabla y, a continuación, se marca como **Deleted**, se quita de la tabla.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [Manipular datos en un objeto DataTable](manipulating-data-in-a-datatable.md)
- [Información general de ADO.NET](../ado-net-overview.md)
