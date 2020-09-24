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
# <a name="datarow-deletion"></a><span data-ttu-id="ed23c-102">Eliminación de DataRow</span><span class="sxs-lookup"><span data-stu-id="ed23c-102">DataRow Deletion</span></span>

<span data-ttu-id="ed23c-103">Hay dos métodos que puede usar para eliminar un <xref:System.Data.DataRow> objeto de un <xref:System.Data.DataTable> objeto: el método **Remove** del <xref:System.Data.DataRowCollection> objeto y el <xref:System.Data.DataRow.Delete%2A> método del objeto **DataRow** .</span><span class="sxs-lookup"><span data-stu-id="ed23c-103">There are two methods you can use to delete a <xref:System.Data.DataRow> object from a <xref:System.Data.DataTable> object: the **Remove** method of the <xref:System.Data.DataRowCollection> object, and the <xref:System.Data.DataRow.Delete%2A> method of the **DataRow** object.</span></span> <span data-ttu-id="ed23c-104">Mientras que el <xref:System.Data.DataRowCollection.Remove%2A> método elimina una **DataRow** de la **DataRowCollection**, el <xref:System.Data.DataRow.Delete%2A> método solo marca la fila para su eliminación.</span><span class="sxs-lookup"><span data-stu-id="ed23c-104">Whereas the <xref:System.Data.DataRowCollection.Remove%2A> method deletes a **DataRow** from the **DataRowCollection**, the <xref:System.Data.DataRow.Delete%2A> method only marks the row for deletion.</span></span> <span data-ttu-id="ed23c-105">La eliminación real se produce cuando la aplicación llama al método **AcceptChanges** .</span><span class="sxs-lookup"><span data-stu-id="ed23c-105">The actual removal occurs when the application calls the **AcceptChanges** method.</span></span> <span data-ttu-id="ed23c-106">Con <xref:System.Data.DataRow.Delete%2A>, se puede comprobar mediante programa qué filas están marcadas para eliminación antes de quitarlas realmente.</span><span class="sxs-lookup"><span data-stu-id="ed23c-106">By using <xref:System.Data.DataRow.Delete%2A>, you can programmatically check which rows are marked for deletion before actually removing them.</span></span> <span data-ttu-id="ed23c-107">Cuando una fila está marcada para eliminación, la propiedad <xref:System.Data.DataRow.RowState%2A> se establece en <xref:System.Data.DataRow.Delete%2A>.</span><span class="sxs-lookup"><span data-stu-id="ed23c-107">When a row is marked for deletion, its <xref:System.Data.DataRow.RowState%2A> property is set to <xref:System.Data.DataRow.Delete%2A>.</span></span>  
  
 <span data-ttu-id="ed23c-108">No se debe llamar a <xref:System.Data.DataRow.Delete%2A> ni a <xref:System.Data.DataRowCollection.Remove%2A> en un bucle foreach durante una iteración a través de un objeto <xref:System.Data.DataRowCollection> .</span><span class="sxs-lookup"><span data-stu-id="ed23c-108">Neither <xref:System.Data.DataRow.Delete%2A> nor <xref:System.Data.DataRowCollection.Remove%2A> should be called in a foreach loop while iterating through a <xref:System.Data.DataRowCollection> object.</span></span> <span data-ttu-id="ed23c-109">Ni <xref:System.Data.DataRow.Delete%2A> ni <xref:System.Data.DataRowCollection.Remove%2A> modifican el estado de la colección.</span><span class="sxs-lookup"><span data-stu-id="ed23c-109"><xref:System.Data.DataRow.Delete%2A> nor <xref:System.Data.DataRowCollection.Remove%2A> modify the state of the collection.</span></span>  
  
 <span data-ttu-id="ed23c-110">Al utilizar un <xref:System.Data.DataSet> **objeto o DataTable** junto con un **DataAdapter** y un origen de datos relacional, utilice el método **Delete** de **DataRow** para quitar la fila.</span><span class="sxs-lookup"><span data-stu-id="ed23c-110">When using a <xref:System.Data.DataSet> or **DataTable** in conjunction with a **DataAdapter** and a relational data source, use the **Delete** method of the **DataRow** to remove the row.</span></span> <span data-ttu-id="ed23c-111">El método **Delete** marca la fila como **eliminada** en el **DataSet** o **DataTable** , pero no la quita.</span><span class="sxs-lookup"><span data-stu-id="ed23c-111">The **Delete** method marks the row as **Deleted** in the **DataSet** or **DataTable** but does not remove it.</span></span> <span data-ttu-id="ed23c-112">En su lugar, cuando el **DataAdapter** encuentra una fila marcada como **Deleted**, ejecuta su método **DeleteCommand** para eliminar la fila en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="ed23c-112">Instead, when the **DataAdapter** encounters a row marked as **Deleted**, it executes its **DeleteCommand** method to delete the row at the data source.</span></span> <span data-ttu-id="ed23c-113">La fila se puede quitar de forma permanente mediante el método **AcceptChanges** .</span><span class="sxs-lookup"><span data-stu-id="ed23c-113">The row can then be permanently removed using the **AcceptChanges** method.</span></span> <span data-ttu-id="ed23c-114">Si utiliza **Remove** para eliminar la fila, la fila se quita completamente de la tabla, pero el **DataAdapter** no eliminará la fila del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="ed23c-114">If you use **Remove** to delete the row, the row is removed entirely from the table, but the **DataAdapter** will not delete the row at the data source.</span></span>  
  
 <span data-ttu-id="ed23c-115">El método **Remove** de la **DataRowCollection** toma un **DataRow** como argumento y lo quita de la colección, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ed23c-115">The **Remove** method of the **DataRowCollection** takes a **DataRow** as an argument and removes it from the collection, as shown in the following example.</span></span>  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 <span data-ttu-id="ed23c-116">En cambio, en el ejemplo siguiente se muestra cómo llamar al método **Delete** en una **DataRow** para cambiar su **RowState** a **Deleted**.</span><span class="sxs-lookup"><span data-stu-id="ed23c-116">In contrast, the following example demonstrates how to call the **Delete** method on a **DataRow** to change its **RowState** to **Deleted**.</span></span>  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 <span data-ttu-id="ed23c-117">Si una fila está marcada para su eliminación y se llama al método **AcceptChanges** del objeto **DataTable** , la fila se quita de la **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="ed23c-117">If a row is marked for deletion and you call the **AcceptChanges** method of the **DataTable** object, the row is removed from the **DataTable**.</span></span> <span data-ttu-id="ed23c-118">Por el contrario, si se llama a **RejectChanges**, el **RowState** de la fila se revierte a lo que era antes de marcarse como **eliminado**.</span><span class="sxs-lookup"><span data-stu-id="ed23c-118">In contrast, if you call **RejectChanges**, the **RowState** of the row reverts to what it was before being marked as **Deleted**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ed23c-119">Si se **agrega**el **RowState** de una **DataRow** , lo que significa que se acaba de agregar a la tabla y, a continuación, se marca como **Deleted**, se quita de la tabla.</span><span class="sxs-lookup"><span data-stu-id="ed23c-119">If the **RowState** of a **DataRow** is **Added**, meaning it has just been added to the table, and it is then marked as **Deleted**, it is removed from the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed23c-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed23c-120">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="ed23c-121">Manipular datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="ed23c-121">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="ed23c-122">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ed23c-122">ADO.NET Overview</span></span>](../ado-net-overview.md)
