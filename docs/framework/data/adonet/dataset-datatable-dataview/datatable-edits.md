---
description: 'Más información acerca de: ediciones de DataTable'
title: Ediciones de DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
ms.openlocfilehash: 983a4016fbdb71baa3bcd4ce8a34175d10b604d2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739474"
---
# <a name="datatable-edits"></a><span data-ttu-id="53988-103">Ediciones de DataTable</span><span class="sxs-lookup"><span data-stu-id="53988-103">DataTable Edits</span></span>

<span data-ttu-id="53988-104">Cuando se cambian los valores de las columnas en una <xref:System.Data.DataRow>, los cambios se sitúan inmediatamente en el estado actual de la fila.</span><span class="sxs-lookup"><span data-stu-id="53988-104">When you make changes to column values in a <xref:System.Data.DataRow>, the changes are immediately placed in the current state of the row.</span></span> <span data-ttu-id="53988-105"><xref:System.Data.DataRowState>A continuación, se establece en **Modified** y se aceptan o se rechazan los cambios mediante los <xref:System.Data.DataRow.AcceptChanges%2A> <xref:System.Data.DataRow.RejectChanges%2A> métodos o de **DataRow**.</span><span class="sxs-lookup"><span data-stu-id="53988-105">The <xref:System.Data.DataRowState> is then set to **Modified**, and the changes are accepted or rejected using the <xref:System.Data.DataRow.AcceptChanges%2A> or <xref:System.Data.DataRow.RejectChanges%2A> methods of the **DataRow**.</span></span> <span data-ttu-id="53988-106">**DataRow** también proporciona tres métodos que se pueden usar para suspender el estado de la fila mientras se edita.</span><span class="sxs-lookup"><span data-stu-id="53988-106">The **DataRow** also provides three methods that you can use to suspend the state of the row while you are editing it.</span></span> <span data-ttu-id="53988-107">Estos métodos son <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> y <xref:System.Data.DataRow.CancelEdit%2A>.</span><span class="sxs-lookup"><span data-stu-id="53988-107">These methods are <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A>, and <xref:System.Data.DataRow.CancelEdit%2A>.</span></span>  
  
 <span data-ttu-id="53988-108">Cuando se modifican directamente los valores de columna en una **DataRow** , el **DataRow** administra los valores de columna mediante las versiones de fila **actual**, **predeterminada** y **original** .</span><span class="sxs-lookup"><span data-stu-id="53988-108">When you modify column values in a **DataRow** directly, the **DataRow** manages the column values using the **Current**, **Default**, and **Original** row versions.</span></span> <span data-ttu-id="53988-109">Además de estas versiones de fila, los métodos **BeginEdit**, **EndEdit** y **CancelEdit** utilizan una cuarta versión de fila: **proposed**.</span><span class="sxs-lookup"><span data-stu-id="53988-109">In addition to these row versions, the **BeginEdit**, **EndEdit**, and **CancelEdit** methods use a fourth row version: **Proposed**.</span></span> <span data-ttu-id="53988-110">Para obtener más información sobre las versiones de fila, vea [Estados de fila y versiones de fila](row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="53988-110">For more information about row versions, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="53988-111">La versión de fila **propuesta** existe durante una operación de edición que comienza llamando a **BeginEdit** y termina bien mediante **EndEdit** o **CancelEdit,** o bien llamando a **AcceptChanges** o **RejectChanges**.</span><span class="sxs-lookup"><span data-stu-id="53988-111">The **Proposed** row version exists during an edit operation that begins by calling **BeginEdit** and that ends either by using **EndEdit** or **CancelEdit,** or by calling **AcceptChanges** or **RejectChanges**.</span></span>  
  
 <span data-ttu-id="53988-112">Durante la operación de edición, puede aplicar la lógica de validación a columnas individuales mediante la evaluación del **ProposedValue** en el evento **ColumnChanged** de la **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="53988-112">During the edit operation, you can apply validation logic to individual columns by evaluating the **ProposedValue** in the **ColumnChanged** event of the **DataTable**.</span></span> <span data-ttu-id="53988-113">El evento **ColumnChanged** contiene **DataColumnChangeEventArgs** que mantienen una referencia a la columna que está cambiando y al **ProposedValue**.</span><span class="sxs-lookup"><span data-stu-id="53988-113">The **ColumnChanged** event holds **DataColumnChangeEventArgs** that keep a reference to the column that is changing and to the **ProposedValue**.</span></span> <span data-ttu-id="53988-114">Después de evaluar el valor propuesto, se puede modificar o cancelar la edición.</span><span class="sxs-lookup"><span data-stu-id="53988-114">After you evaluate the proposed value, you can either modify it or cancel the edit.</span></span> <span data-ttu-id="53988-115">Una vez finalizada la edición, la fila sale del estado **propuesto** .</span><span class="sxs-lookup"><span data-stu-id="53988-115">When the edit is ended, the row moves out of the **Proposed** state.</span></span>  
  
 <span data-ttu-id="53988-116">Puede confirmar las ediciones llamando a **EndEdit** o puede cancelarlas llamando a **CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="53988-116">You can confirm edits by calling **EndEdit**, or you can cancel them by calling **CancelEdit**.</span></span> <span data-ttu-id="53988-117">Tenga en cuenta que mientras **EndEdit** confirma las modificaciones, el **conjunto** de cambios no acepta realmente los cambios hasta que se llama a **AcceptChanges** .</span><span class="sxs-lookup"><span data-stu-id="53988-117">Note that while **EndEdit** does confirm your edits, the **DataSet** does not actually accept the changes until **AcceptChanges** is called.</span></span> <span data-ttu-id="53988-118">Tenga en cuenta también que si llama a **AcceptChanges** antes de finalizar la edición con **EndEdit** o **CancelEdit**, se finaliza la edición y se aceptan los valores de fila **propuestos** para las versiones de fila **actuales** y **originales** .</span><span class="sxs-lookup"><span data-stu-id="53988-118">Note also that if you call **AcceptChanges** before you have ended the edit with **EndEdit** or **CancelEdit**, the edit is ended and the **Proposed** row values are accepted for both the **Current** and **Original** row versions.</span></span> <span data-ttu-id="53988-119">Del mismo modo, si se llama a **RejectChanges** , se finaliza la edición y se descartan las versiones de fila **actuales** y **propuestas** .</span><span class="sxs-lookup"><span data-stu-id="53988-119">In the same manner, calling **RejectChanges** ends the edit and discards the **Current** and **Proposed** row versions.</span></span> <span data-ttu-id="53988-120">Llamar a **EndEdit** o **CancelEdit** después de llamar a **AcceptChanges** o **RejectChanges** no tiene ningún efecto porque la edición ya ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="53988-120">Calling **EndEdit** or **CancelEdit** after calling **AcceptChanges** or **RejectChanges** has no effect because the edit has already ended.</span></span>  
  
 <span data-ttu-id="53988-121">En el ejemplo siguiente se muestra cómo usar **BeginEdit** con **EndEdit** y **CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="53988-121">The following example demonstrates how to use **BeginEdit** with **EndEdit** and **CancelEdit**.</span></span> <span data-ttu-id="53988-122">En el ejemplo también se comprueba **ProposedValue** del evento **ColumnChanged** y se decide si se va a cancelar la edición.</span><span class="sxs-lookup"><span data-stu-id="53988-122">The example also checks the **ProposedValue** in the **ColumnChanged** event and decides whether to cancel the edit.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="53988-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="53988-123">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataRowVersion>
- [<span data-ttu-id="53988-124">Manipular datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="53988-124">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="53988-125">Controlar eventos de DataTable</span><span class="sxs-lookup"><span data-stu-id="53988-125">Handling DataTable Events</span></span>](handling-datatable-events.md)
- [<span data-ttu-id="53988-126">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="53988-126">ADO.NET Overview</span></span>](../ado-net-overview.md)
