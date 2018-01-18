---
title: Ediciones de DataTable
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
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 82fda2b5e92746b36ab7eb14eb645eca75e1e4bb
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="datatable-edits"></a><span data-ttu-id="1e6f9-102">Ediciones de DataTable</span><span class="sxs-lookup"><span data-stu-id="1e6f9-102">DataTable Edits</span></span>
<span data-ttu-id="1e6f9-103">Cuando se cambian los valores de las columnas en una <xref:System.Data.DataRow>, los cambios se sitúan inmediatamente en el estado actual de la fila.</span><span class="sxs-lookup"><span data-stu-id="1e6f9-103">When you make changes to column values in a <xref:System.Data.DataRow>, the changes are immediately placed in the current state of the row.</span></span> <span data-ttu-id="1e6f9-104">El <xref:System.Data.DataRowState> , a continuación, se establece en **Modified**, y los cambios se aceptan o rechazan mediante el <xref:System.Data.DataRow.AcceptChanges%2A> o <xref:System.Data.DataRow.RejectChanges%2A> métodos de la **DataRow**.</span><span class="sxs-lookup"><span data-stu-id="1e6f9-104">The <xref:System.Data.DataRowState> is then set to **Modified**, and the changes are accepted or rejected using the <xref:System.Data.DataRow.AcceptChanges%2A> or <xref:System.Data.DataRow.RejectChanges%2A> methods of the **DataRow**.</span></span> <span data-ttu-id="1e6f9-105">El **DataRow** proporciona también tres métodos que puede usar para suspender el estado de la fila mientras se está editando.</span><span class="sxs-lookup"><span data-stu-id="1e6f9-105">The **DataRow** also provides three methods that you can use to suspend the state of the row while you are editing it.</span></span> <span data-ttu-id="1e6f9-106">Estos métodos son <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> y <xref:System.Data.DataRow.CancelEdit%2A>.</span><span class="sxs-lookup"><span data-stu-id="1e6f9-106">These methods are <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A>, and <xref:System.Data.DataRow.CancelEdit%2A>.</span></span>  
  
 <span data-ttu-id="1e6f9-107">Al modificar los valores de columna en una **DataRow** directamente, la **DataRow** administra los valores de columna mediante el **actual**, **predeterminado**, y **Original** versiones de fila.</span><span class="sxs-lookup"><span data-stu-id="1e6f9-107">When you modify column values in a **DataRow** directly, the **DataRow** manages the column values using the **Current**, **Default**, and **Original** row versions.</span></span> <span data-ttu-id="1e6f9-108">Además de estas versiones de fila, el **BeginEdit**, **EndEdit**, y **CancelEdit** métodos utilizan una cuarta versión de fila: **propuesto**.</span><span class="sxs-lookup"><span data-stu-id="1e6f9-108">In addition to these row versions, the **BeginEdit**, **EndEdit**, and **CancelEdit** methods use a fourth row version: **Proposed**.</span></span> <span data-ttu-id="1e6f9-109">Para obtener más información acerca de las versiones de fila, vea [Estados de fila y versiones de fila](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="1e6f9-109">For more information about row versions, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="1e6f9-110">El **propuesto** versión de fila existe mientras dura una operación de edición que se inicia mediante una llamada a **BeginEdit** y finaliza mediante el uso de **EndEdit** o **CancelEdit,**  o mediante una llamada a **AcceptChanges** o **RejectChanges**.</span><span class="sxs-lookup"><span data-stu-id="1e6f9-110">The **Proposed** row version exists during an edit operation that begins by calling **BeginEdit** and that ends either by using **EndEdit** or **CancelEdit,** or by calling **AcceptChanges** or **RejectChanges**.</span></span>  
  
 <span data-ttu-id="1e6f9-111">Durante la operación de edición, puede aplicar lógica de validación a las columnas individualmente evaluando el **ProposedValue** en el **ColumnChanged** eventos de la **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="1e6f9-111">During the edit operation, you can apply validation logic to individual columns by evaluating the **ProposedValue** in the **ColumnChanged** event of the **DataTable**.</span></span> <span data-ttu-id="1e6f9-112">El **ColumnChanged** contiene eventos **DataColumnChangeEventArgs** que guardan una referencia a la columna que está cambiando a la **ProposedValue**.</span><span class="sxs-lookup"><span data-stu-id="1e6f9-112">The **ColumnChanged** event holds **DataColumnChangeEventArgs** that keep a reference to the column that is changing and to the **ProposedValue**.</span></span> <span data-ttu-id="1e6f9-113">Después de evaluar el valor propuesto, se puede modificar o cancelar la edición.</span><span class="sxs-lookup"><span data-stu-id="1e6f9-113">After you evaluate the proposed value, you can either modify it or cancel the edit.</span></span> <span data-ttu-id="1e6f9-114">Cuando finaliza la edición, la fila se mueve fuera de la **propuesto** estado.</span><span class="sxs-lookup"><span data-stu-id="1e6f9-114">When the edit is ended, the row moves out of the **Proposed** state.</span></span>  
  
 <span data-ttu-id="1e6f9-115">Modificaciones se pueden confirmar llamando a **EndEdit**, o se puede cancelar mediante una llamada a **CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="1e6f9-115">You can confirm edits by calling **EndEdit**, or you can cancel them by calling **CancelEdit**.</span></span> <span data-ttu-id="1e6f9-116">Tenga en cuenta que mientras **EndEdit** confirma las modificaciones, el **conjunto de datos** no las acepta realmente hasta que **AcceptChanges** se llama.</span><span class="sxs-lookup"><span data-stu-id="1e6f9-116">Note that while **EndEdit** does confirm your edits, the **DataSet** does not actually accept the changes until **AcceptChanges** is called.</span></span> <span data-ttu-id="1e6f9-117">Tenga en cuenta también que si se llama a **AcceptChanges** antes de que haya finalizado la edición con **EndEdit** o **CancelEdit**, dicha edición finaliza y la **propuesto** se aceptan valores de fila tanto para el **actual** y **Original** versiones de fila.</span><span class="sxs-lookup"><span data-stu-id="1e6f9-117">Note also that if you call **AcceptChanges** before you have ended the edit with **EndEdit** or **CancelEdit**, the edit is ended and the **Proposed** row values are accepted for both the **Current** and **Original** row versions.</span></span> <span data-ttu-id="1e6f9-118">De la misma manera, una llamada a **RejectChanges** finaliza la edición y descarta el **actual** y **propuesto** versiones de fila.</span><span class="sxs-lookup"><span data-stu-id="1e6f9-118">In the same manner, calling **RejectChanges** ends the edit and discards the **Current** and **Proposed** row versions.</span></span> <span data-ttu-id="1e6f9-119">Al llamar a **EndEdit** o **CancelEdit** después de llamar a **AcceptChanges** o **RejectChanges** no tiene ningún efecto porque la edición ya ha ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="1e6f9-119">Calling **EndEdit** or **CancelEdit** after calling **AcceptChanges** or **RejectChanges** has no effect because the edit has already ended.</span></span>  
  
 <span data-ttu-id="1e6f9-120">En el ejemplo siguiente se muestra cómo usar **BeginEdit** con **EndEdit** y **CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="1e6f9-120">The following example demonstrates how to use **BeginEdit** with **EndEdit** and **CancelEdit**.</span></span> <span data-ttu-id="1e6f9-121">El ejemplo también se comprueba la **ProposedValue** en el **ColumnChanged** eventos y se decide si cancelar la edición.</span><span class="sxs-lookup"><span data-stu-id="1e6f9-121">The example also checks the **ProposedValue** in the **ColumnChanged** event and decides whether to cancel the edit.</span></span>  
  
```vb  
Dim workTable As DataTable = New DataTable  
workTable.Columns.Add("LastName", Type.GetType("System.String"))  
  
AddHandler workTable.ColumnChanged, _  
  New DataColumnChangeEventHandler(AddressOf OnColumnChanged)  
  
Dim workRow As DataRow = workTable.NewRow()  
workRow(0) = "Smith"  
workTable.Rows.Add(workRow)  
  
workRow.BeginEdit()  
' Causes the ColumnChanged event to write a message and cancel the edit.  
workRow(0) = ""       
workRow.EndEdit()  
  
' Displays "Smith, New".  
Console.WriteLine("{0}, {1}", workRow(0), workRow.RowState)  
  
Private Shared Sub OnColumnChanged( _  
  sender As Object, args As DataColumnChangeEventArgs)  
  If args.Column.ColumnName = "LastName" Then  
    If args.ProposedValue.ToString() = "" Then  
      Console.WriteLine("Last Name cannot be blank.  Edit canceled.")  
      args.Row.CancelEdit()  
    End If  
  End If  
End Sub  
```  
  
```csharp  
DataTable workTable  = new DataTable();  
workTable.Columns.Add("LastName", typeof(String));  
  
workTable.ColumnChanged +=   
  new DataColumnChangeEventHandler(OnColumnChanged);  
  
DataRow workRow = workTable.NewRow();  
workRow[0] = "Smith";  
workTable.Rows.Add(workRow);  
  
workRow.BeginEdit();  
// Causes the ColumnChanged event to write a message and cancel the edit.  
workRow[0] = "";       
workRow.EndEdit();  
  
// Displays "Smith, New".  
Console.WriteLine("{0}, {1}", workRow[0], workRow.RowState);    
  
protected static void OnColumnChanged(  
  Object sender, DataColumnChangeEventArgs args)  
{  
  if (args.Column.ColumnName == "LastName")  
    if (args.ProposedValue.ToString() == "")  
    {  
      Console.WriteLine("Last Name cannot be blank. Edit canceled.");  
      args.Row.CancelEdit();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="1e6f9-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e6f9-122">See Also</span></span>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataRowVersion>  
 [<span data-ttu-id="1e6f9-123">Manipulación de datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="1e6f9-123">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="1e6f9-124">Control de eventos de DataTable</span><span class="sxs-lookup"><span data-stu-id="1e6f9-124">Handling DataTable Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 [<span data-ttu-id="1e6f9-125">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="1e6f9-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
