---
title: "Editar DataTable | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Editar DataTable
Cuando se cambian los valores de las columnas en una <xref:System.Data.DataRow>, los cambios se sitúan inmediatamente en el estado actual de la fila.  A continuación, el <xref:System.Data.DataRowState> se establece en **Modified** y los cambios se aceptan o se rechazan mediante los métodos <xref:System.Data.DataRow.AcceptChanges%2A> o <xref:System.Data.DataRow.RejectChanges%2A> de la **DataRow**.  **DataRow** proporciona también tres métodos que se pueden usar para suspender el estado de la fila mientras se está editando.  Estos métodos son <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> y <xref:System.Data.DataRow.CancelEdit%2A>.  
  
 Cuando se modifican los valores de columna de una **DataRow** directamente, **DataRow** administra los valores de columna mediante las versiones de fila **Current**, **Default** y **Original**.  Además de estas versiones de fila, los métodos **BeginEdit**, **EndEdit** y **CancelEdit** utilizan una cuarta versión de fila: **Proposed**.  Para obtener más información sobre versiones de fila, vea [Estados de fila y versiones de fila](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
 La versión de fila **Proposed** propuesta existe mientras dura una operación de edición que se inicia llamando a **BeginEdit** y finaliza mediante **EndEdit** o **CancelEdit,** o bien llamando a **AcceptChanges** o **RejectChanges**.  
  
 Durante la operación de edición se puede aplicar la lógica de validación a las columnas individualmente evaluando el **ProposedValue** del evento **ColumnChanged** de la **DataTable**.  El evento **ColumnChanged** contiene **DataColumnChangeEventArgs** que guardan una referencia a la columna que se está cambiando y al **ProposedValue**.  Después de evaluar el valor propuesto, se puede modificar o cancelar la edición.  Cuando termina la operación de edición, la fila abandona el estado de **Proposed**.  
  
 Las modificaciones se pueden confirmar llamando a **EndEdit** o cancelar llamando a **CancelEdit**.  Tenga en cuenta que aunque **EndEdit** confirma las modificaciones, **DataSet** no las acepta realmente hasta que se llama a **AcceptChanges**.  También hay que tener en cuenta que si se llama a **AcceptChanges** antes de finalizar la operación de edición con **EndEdit** o **CancelEdit**, dicha edición finaliza y los valores de fila **Proposed** se aceptan en las dos versiones de fila: **Current** y **Original**.  De la misma manera, si se llama a **RejectChanges**, se finaliza la edición y se descartan las versiones de fila **Current** y **Proposed**.  Una llamada a **EndEdit** o **CancelEdit** después de llamar a **AcceptChanges** o **RejectChanges** no tiene ningún efecto porque la edición ya ha finalizado.  
  
 En el ejemplo siguiente se muestra cómo se utilizan **BeginEdit** con **EndEdit** y **CancelEdit**.  En el ejemplo también se comprueba el **ProposedValue** del evento **ColumnChanged** y se decide si cancelar la edición.  
  
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
  
## Vea también  
 <xref:System.Data.DataRow>   
 <xref:System.Data.DataTable>   
 <xref:System.Data.DataRowVersion>   
 [Manipular datos en DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)   
 [Control de eventos DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)