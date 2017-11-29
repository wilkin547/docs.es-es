---
title: "Eliminación de DataRow"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f9eb89d711cbf66f3b6816e597c14359be1f3639
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="datarow-deletion"></a><span data-ttu-id="71f85-102">Eliminación de DataRow</span><span class="sxs-lookup"><span data-stu-id="71f85-102">DataRow Deletion</span></span>
<span data-ttu-id="71f85-103">Hay dos métodos que puede usar para eliminar un <xref:System.Data.DataRow> objeto desde un <xref:System.Data.DataTable> objeto: el **quitar** método de la <xref:System.Data.DataRowCollection> objeto y el <xref:System.Data.DataRow.Delete%2A> método de la **DataRow**objeto.</span><span class="sxs-lookup"><span data-stu-id="71f85-103">There are two methods you can use to delete a <xref:System.Data.DataRow> object from a <xref:System.Data.DataTable> object: the **Remove** method of the <xref:System.Data.DataRowCollection> object, and the <xref:System.Data.DataRow.Delete%2A> method of the **DataRow** object.</span></span> <span data-ttu-id="71f85-104">Mientras que la <xref:System.Data.DataRowCollection.Remove%2A> método elimina un **DataRow** desde el **DataRowCollection**, el <xref:System.Data.DataRow.Delete%2A> método solo marca la fila para su eliminación.</span><span class="sxs-lookup"><span data-stu-id="71f85-104">Whereas the <xref:System.Data.DataRowCollection.Remove%2A> method deletes a **DataRow** from the **DataRowCollection**, the <xref:System.Data.DataRow.Delete%2A> method only marks the row for deletion.</span></span> <span data-ttu-id="71f85-105">La eliminación propiamente dicha se produce cuando la aplicación llama a la **AcceptChanges** método.</span><span class="sxs-lookup"><span data-stu-id="71f85-105">The actual removal occurs when the application calls the **AcceptChanges** method.</span></span> <span data-ttu-id="71f85-106">Con <xref:System.Data.DataRow.Delete%2A>, se puede comprobar mediante programa qué filas están marcadas para eliminación antes de quitarlas realmente.</span><span class="sxs-lookup"><span data-stu-id="71f85-106">By using <xref:System.Data.DataRow.Delete%2A>, you can programmatically check which rows are marked for deletion before actually removing them.</span></span> <span data-ttu-id="71f85-107">Cuando una fila está marcada para eliminación, la propiedad <xref:System.Data.DataRow.RowState%2A> se establece en <xref:System.Data.DataRow.Delete%2A>.</span><span class="sxs-lookup"><span data-stu-id="71f85-107">When a row is marked for deletion, its <xref:System.Data.DataRow.RowState%2A> property is set to <xref:System.Data.DataRow.Delete%2A>.</span></span>  
  
 <span data-ttu-id="71f85-108">No se debe llamar a <xref:System.Data.DataRow.Delete%2A> ni a <xref:System.Data.DataRowCollection.Remove%2A> en un bucle foreach durante una iteración a través de un objeto <xref:System.Data.DataRowCollection> .</span><span class="sxs-lookup"><span data-stu-id="71f85-108">Neither <xref:System.Data.DataRow.Delete%2A> nor <xref:System.Data.DataRowCollection.Remove%2A> should be called in a foreach loop while iterating through a <xref:System.Data.DataRowCollection> object.</span></span> <span data-ttu-id="71f85-109">Ni <xref:System.Data.DataRow.Delete%2A> ni <xref:System.Data.DataRowCollection.Remove%2A> modifican el estado de la colección.</span><span class="sxs-lookup"><span data-stu-id="71f85-109"><xref:System.Data.DataRow.Delete%2A> nor <xref:System.Data.DataRowCollection.Remove%2A> modify the state of the collection.</span></span>  
  
 <span data-ttu-id="71f85-110">Cuando se usa un <xref:System.Data.DataSet> o **DataTable** junto con un **DataAdapter** y un origen de datos relacional, utilice la **eliminar** método de la  **DataRow** para quitar la fila.</span><span class="sxs-lookup"><span data-stu-id="71f85-110">When using a <xref:System.Data.DataSet> or **DataTable** in conjunction with a **DataAdapter** and a relational data source, use the **Delete** method of the **DataRow** to remove the row.</span></span> <span data-ttu-id="71f85-111">El **eliminar** método marca la fila como **Deleted** en el **conjunto de datos** o **DataTable** pero no se quita.</span><span class="sxs-lookup"><span data-stu-id="71f85-111">The **Delete** method marks the row as **Deleted** in the **DataSet** or **DataTable** but does not remove it.</span></span> <span data-ttu-id="71f85-112">En su lugar, cuando la **DataAdapter** encuentra una fila marcada como **Deleted**, ejecuta su **DeleteCommand** método para eliminar la fila en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="71f85-112">Instead, when the **DataAdapter** encounters a row marked as **Deleted**, it executes its **DeleteCommand** method to delete the row at the data source.</span></span> <span data-ttu-id="71f85-113">La fila puede, a continuación, puede quitar permanentemente usando el **AcceptChanges** método.</span><span class="sxs-lookup"><span data-stu-id="71f85-113">The row can then be permanently removed using the **AcceptChanges** method.</span></span> <span data-ttu-id="71f85-114">Si usa **quitar** para eliminar la fila, la fila se quita por completo de la tabla, pero la **DataAdapter** no eliminará la fila del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="71f85-114">If you use **Remove** to delete the row, the row is removed entirely from the table, but the **DataAdapter** will not delete the row at the data source.</span></span>  
  
 <span data-ttu-id="71f85-115">El **quitar** método de la **DataRowCollection** toma una **DataRow** como argumento y la quita de la colección, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="71f85-115">The **Remove** method of the **DataRowCollection** takes a **DataRow** as an argument and removes it from the collection, as shown in the following example.</span></span>  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 <span data-ttu-id="71f85-116">En cambio, en el ejemplo siguiente se muestra cómo llamar a la **eliminar** método en un **DataRow** para cambiar su **RowState** a **Deleted** .</span><span class="sxs-lookup"><span data-stu-id="71f85-116">In contrast, the following example demonstrates how to call the **Delete** method on a **DataRow** to change its **RowState** to **Deleted**.</span></span>  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 <span data-ttu-id="71f85-117">Si una fila está marcada para su eliminación y se llama el **AcceptChanges** método de la **DataTable** objeto, la fila se quita de la **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="71f85-117">If a row is marked for deletion and you call the **AcceptChanges** method of the **DataTable** object, the row is removed from the **DataTable**.</span></span> <span data-ttu-id="71f85-118">En cambio, si se llama a **RejectChanges**, **RowState** de la fila vuelve al que tenía antes de que se marcara como **Deleted**.</span><span class="sxs-lookup"><span data-stu-id="71f85-118">In contrast, if you call **RejectChanges**, the **RowState** of the row reverts to what it was before being marked as **Deleted**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71f85-119">Si el **RowState** de un **DataRow** es **Added**, lo que significa que se acaba de agregar a la tabla y, a continuación, se marca como **Deleted**, es Quita de la tabla.</span><span class="sxs-lookup"><span data-stu-id="71f85-119">If the **RowState** of a **DataRow** is **Added**, meaning it has just been added to the table, and it is then marked as **Deleted**, it is removed from the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71f85-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="71f85-120">See Also</span></span>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataRowCollection>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="71f85-121">Manipular datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="71f85-121">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="71f85-122">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="71f85-122">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
