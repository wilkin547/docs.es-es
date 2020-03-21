---
title: Ediciones de DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
ms.openlocfilehash: 9e8c4204b51121b147fc7614066d9b849a687574
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151265"
---
# <a name="datatable-edits"></a><span data-ttu-id="60840-102">Ediciones de DataTable</span><span class="sxs-lookup"><span data-stu-id="60840-102">DataTable Edits</span></span>
<span data-ttu-id="60840-103">Cuando se cambian los valores de las columnas en una <xref:System.Data.DataRow>, los cambios se sitúan inmediatamente en el estado actual de la fila.</span><span class="sxs-lookup"><span data-stu-id="60840-103">When you make changes to column values in a <xref:System.Data.DataRow>, the changes are immediately placed in the current state of the row.</span></span> <span data-ttu-id="60840-104">A <xref:System.Data.DataRowState> continuación, se establece en **Modificado**y los <xref:System.Data.DataRow.AcceptChanges%2A> cambios se aceptan o rechazan mediante los métodos o <xref:System.Data.DataRow.RejectChanges%2A> de **DataRow**.</span><span class="sxs-lookup"><span data-stu-id="60840-104">The <xref:System.Data.DataRowState> is then set to **Modified**, and the changes are accepted or rejected using the <xref:System.Data.DataRow.AcceptChanges%2A> or <xref:System.Data.DataRow.RejectChanges%2A> methods of the **DataRow**.</span></span> <span data-ttu-id="60840-105">**El DataRow** también proporciona tres métodos que puede usar para suspender el estado de la fila mientras se está editando.</span><span class="sxs-lookup"><span data-stu-id="60840-105">The **DataRow** also provides three methods that you can use to suspend the state of the row while you are editing it.</span></span> <span data-ttu-id="60840-106">Estos métodos son <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> y <xref:System.Data.DataRow.CancelEdit%2A>.</span><span class="sxs-lookup"><span data-stu-id="60840-106">These methods are <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A>, and <xref:System.Data.DataRow.CancelEdit%2A>.</span></span>  
  
 <span data-ttu-id="60840-107">Al modificar los valores de columna en un **DataRow** directamente, **el DataRow** administra los valores de columna mediante las versiones de fila **Actual**, **Predeterminado**y **Original.**</span><span class="sxs-lookup"><span data-stu-id="60840-107">When you modify column values in a **DataRow** directly, the **DataRow** manages the column values using the **Current**, **Default**, and **Original** row versions.</span></span> <span data-ttu-id="60840-108">Además de estas versiones de fila, los métodos **BeginEdit**, **EndEdit**y **CancelEdit** utilizan una cuarta versión de fila: **Proposed**.</span><span class="sxs-lookup"><span data-stu-id="60840-108">In addition to these row versions, the **BeginEdit**, **EndEdit**, and **CancelEdit** methods use a fourth row version: **Proposed**.</span></span> <span data-ttu-id="60840-109">Para obtener más información acerca de las versiones de fila, vea Estados de fila [y versiones](row-states-and-row-versions.md)de fila .</span><span class="sxs-lookup"><span data-stu-id="60840-109">For more information about row versions, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="60840-110">La versión de fila **Propuesta** existe durante una operación de edición que comienza llamando a **BeginEdit** y que finaliza mediante **EndEdit** o **CancelEdit,** o llamando a **AcceptChanges** o **RejectChanges**.</span><span class="sxs-lookup"><span data-stu-id="60840-110">The **Proposed** row version exists during an edit operation that begins by calling **BeginEdit** and that ends either by using **EndEdit** or **CancelEdit,** or by calling **AcceptChanges** or **RejectChanges**.</span></span>  
  
 <span data-ttu-id="60840-111">Durante la operación de edición, puede aplicar lógica de validación a columnas individuales evaluando **ProposedValue** en el evento **ColumnChanged** de **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="60840-111">During the edit operation, you can apply validation logic to individual columns by evaluating the **ProposedValue** in the **ColumnChanged** event of the **DataTable**.</span></span> <span data-ttu-id="60840-112">El evento **ColumnChanged** contiene **DataColumnChangeEventArgs** que mantienen una referencia a la columna que está cambiando y a **ProposedValue**.</span><span class="sxs-lookup"><span data-stu-id="60840-112">The **ColumnChanged** event holds **DataColumnChangeEventArgs** that keep a reference to the column that is changing and to the **ProposedValue**.</span></span> <span data-ttu-id="60840-113">Después de evaluar el valor propuesto, se puede modificar o cancelar la edición.</span><span class="sxs-lookup"><span data-stu-id="60840-113">After you evaluate the proposed value, you can either modify it or cancel the edit.</span></span> <span data-ttu-id="60840-114">Cuando finaliza la edición, la fila sale del estado **Propuesto.**</span><span class="sxs-lookup"><span data-stu-id="60840-114">When the edit is ended, the row moves out of the **Proposed** state.</span></span>  
  
 <span data-ttu-id="60840-115">Puede confirmar ediciones llamando a **EndEdit**o cancelarlas llamando a **CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="60840-115">You can confirm edits by calling **EndEdit**, or you can cancel them by calling **CancelEdit**.</span></span> <span data-ttu-id="60840-116">Tenga en cuenta que mientras **EndEdit** confirma las ediciones, el **DataSet** no acepta realmente los cambios hasta **AcceptChanges** se llama.</span><span class="sxs-lookup"><span data-stu-id="60840-116">Note that while **EndEdit** does confirm your edits, the **DataSet** does not actually accept the changes until **AcceptChanges** is called.</span></span> <span data-ttu-id="60840-117">Tenga en cuenta también que si llama a **AcceptChanges** antes de finalizar la edición con **EndEdit** o **CancelEdit**, la edición finaliza y se aceptan los valores de fila **propuestos** para las versiones de fila **Actual** y **Original.**</span><span class="sxs-lookup"><span data-stu-id="60840-117">Note also that if you call **AcceptChanges** before you have ended the edit with **EndEdit** or **CancelEdit**, the edit is ended and the **Proposed** row values are accepted for both the **Current** and **Original** row versions.</span></span> <span data-ttu-id="60840-118">De la misma manera, al llamar a **RejectChanges** finaliza la edición y se descartan las versiones de fila **Actual** y **Propuesta.**</span><span class="sxs-lookup"><span data-stu-id="60840-118">In the same manner, calling **RejectChanges** ends the edit and discards the **Current** and **Proposed** row versions.</span></span> <span data-ttu-id="60840-119">Llamar a **EndEdit** o **CancelEdit** después de llamar a **AcceptChanges** o **RejectChanges** no tiene ningún efecto porque la edición ya ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="60840-119">Calling **EndEdit** or **CancelEdit** after calling **AcceptChanges** or **RejectChanges** has no effect because the edit has already ended.</span></span>  
  
 <span data-ttu-id="60840-120">En el ejemplo siguiente se muestra cómo utilizar **BeginEdit** con **EndEdit** y **CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="60840-120">The following example demonstrates how to use **BeginEdit** with **EndEdit** and **CancelEdit**.</span></span> <span data-ttu-id="60840-121">En el ejemplo también se comprueba **el ProposedValue** en el **ColumnChanged** eventos y decide si se debe cancelar la edición.</span><span class="sxs-lookup"><span data-stu-id="60840-121">The example also checks the **ProposedValue** in the **ColumnChanged** event and decides whether to cancel the edit.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="60840-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="60840-122">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataRowVersion>
- [<span data-ttu-id="60840-123">Manipular datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="60840-123">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="60840-124">Control de eventos de DataTable</span><span class="sxs-lookup"><span data-stu-id="60840-124">Handling DataTable Events</span></span>](handling-datatable-events.md)
- [<span data-ttu-id="60840-125">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="60840-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
