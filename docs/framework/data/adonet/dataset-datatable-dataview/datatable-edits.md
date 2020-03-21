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
# <a name="datatable-edits"></a>Ediciones de DataTable
Cuando se cambian los valores de las columnas en una <xref:System.Data.DataRow>, los cambios se sitúan inmediatamente en el estado actual de la fila. A <xref:System.Data.DataRowState> continuación, se establece en **Modificado**y los <xref:System.Data.DataRow.AcceptChanges%2A> cambios se aceptan o rechazan mediante los métodos o <xref:System.Data.DataRow.RejectChanges%2A> de **DataRow**. **El DataRow** también proporciona tres métodos que puede usar para suspender el estado de la fila mientras se está editando. Estos métodos son <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> y <xref:System.Data.DataRow.CancelEdit%2A>.  
  
 Al modificar los valores de columna en un **DataRow** directamente, **el DataRow** administra los valores de columna mediante las versiones de fila **Actual**, **Predeterminado**y **Original.** Además de estas versiones de fila, los métodos **BeginEdit**, **EndEdit**y **CancelEdit** utilizan una cuarta versión de fila: **Proposed**. Para obtener más información acerca de las versiones de fila, vea Estados de fila [y versiones](row-states-and-row-versions.md)de fila .  
  
 La versión de fila **Propuesta** existe durante una operación de edición que comienza llamando a **BeginEdit** y que finaliza mediante **EndEdit** o **CancelEdit,** o llamando a **AcceptChanges** o **RejectChanges**.  
  
 Durante la operación de edición, puede aplicar lógica de validación a columnas individuales evaluando **ProposedValue** en el evento **ColumnChanged** de **DataTable**. El evento **ColumnChanged** contiene **DataColumnChangeEventArgs** que mantienen una referencia a la columna que está cambiando y a **ProposedValue**. Después de evaluar el valor propuesto, se puede modificar o cancelar la edición. Cuando finaliza la edición, la fila sale del estado **Propuesto.**  
  
 Puede confirmar ediciones llamando a **EndEdit**o cancelarlas llamando a **CancelEdit**. Tenga en cuenta que mientras **EndEdit** confirma las ediciones, el **DataSet** no acepta realmente los cambios hasta **AcceptChanges** se llama. Tenga en cuenta también que si llama a **AcceptChanges** antes de finalizar la edición con **EndEdit** o **CancelEdit**, la edición finaliza y se aceptan los valores de fila **propuestos** para las versiones de fila **Actual** y **Original.** De la misma manera, al llamar a **RejectChanges** finaliza la edición y se descartan las versiones de fila **Actual** y **Propuesta.** Llamar a **EndEdit** o **CancelEdit** después de llamar a **AcceptChanges** o **RejectChanges** no tiene ningún efecto porque la edición ya ha finalizado.  
  
 En el ejemplo siguiente se muestra cómo utilizar **BeginEdit** con **EndEdit** y **CancelEdit**. En el ejemplo también se comprueba **el ProposedValue** en el **ColumnChanged** eventos y decide si se debe cancelar la edición.  
  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataRowVersion>
- [Manipular datos en un objeto DataTable](manipulating-data-in-a-datatable.md)
- [Control de eventos de DataTable](handling-datatable-events.md)
- [Información general de ADO.NET](../ado-net-overview.md)
