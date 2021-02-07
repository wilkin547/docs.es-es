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
# <a name="datatable-edits"></a>Ediciones de DataTable

Cuando se cambian los valores de las columnas en una <xref:System.Data.DataRow>, los cambios se sitúan inmediatamente en el estado actual de la fila. <xref:System.Data.DataRowState>A continuación, se establece en **Modified** y se aceptan o se rechazan los cambios mediante los <xref:System.Data.DataRow.AcceptChanges%2A> <xref:System.Data.DataRow.RejectChanges%2A> métodos o de **DataRow**. **DataRow** también proporciona tres métodos que se pueden usar para suspender el estado de la fila mientras se edita. Estos métodos son <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> y <xref:System.Data.DataRow.CancelEdit%2A>.  
  
 Cuando se modifican directamente los valores de columna en una **DataRow** , el **DataRow** administra los valores de columna mediante las versiones de fila **actual**, **predeterminada** y **original** . Además de estas versiones de fila, los métodos **BeginEdit**, **EndEdit** y **CancelEdit** utilizan una cuarta versión de fila: **proposed**. Para obtener más información sobre las versiones de fila, vea [Estados de fila y versiones de fila](row-states-and-row-versions.md).  
  
 La versión de fila **propuesta** existe durante una operación de edición que comienza llamando a **BeginEdit** y termina bien mediante **EndEdit** o **CancelEdit,** o bien llamando a **AcceptChanges** o **RejectChanges**.  
  
 Durante la operación de edición, puede aplicar la lógica de validación a columnas individuales mediante la evaluación del **ProposedValue** en el evento **ColumnChanged** de la **DataTable**. El evento **ColumnChanged** contiene **DataColumnChangeEventArgs** que mantienen una referencia a la columna que está cambiando y al **ProposedValue**. Después de evaluar el valor propuesto, se puede modificar o cancelar la edición. Una vez finalizada la edición, la fila sale del estado **propuesto** .  
  
 Puede confirmar las ediciones llamando a **EndEdit** o puede cancelarlas llamando a **CancelEdit**. Tenga en cuenta que mientras **EndEdit** confirma las modificaciones, el **conjunto** de cambios no acepta realmente los cambios hasta que se llama a **AcceptChanges** . Tenga en cuenta también que si llama a **AcceptChanges** antes de finalizar la edición con **EndEdit** o **CancelEdit**, se finaliza la edición y se aceptan los valores de fila **propuestos** para las versiones de fila **actuales** y **originales** . Del mismo modo, si se llama a **RejectChanges** , se finaliza la edición y se descartan las versiones de fila **actuales** y **propuestas** . Llamar a **EndEdit** o **CancelEdit** después de llamar a **AcceptChanges** o **RejectChanges** no tiene ningún efecto porque la edición ya ha finalizado.  
  
 En el ejemplo siguiente se muestra cómo usar **BeginEdit** con **EndEdit** y **CancelEdit**. En el ejemplo también se comprueba **ProposedValue** del evento **ColumnChanged** y se decide si se va a cancelar la edición.  
  
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
  
## <a name="see-also"></a>Vea también

- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataRowVersion>
- [Manipular datos en un objeto DataTable](manipulating-data-in-a-datatable.md)
- [Controlar eventos de DataTable](handling-datatable-events.md)
- [Información general de ADO.NET](../ado-net-overview.md)
