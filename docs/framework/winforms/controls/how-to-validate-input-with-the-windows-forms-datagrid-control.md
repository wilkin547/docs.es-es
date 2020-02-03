---
title: Validar la entrada con el control DataGrid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid control [Windows Forms], examples
- user input [Windows Forms], validating
- examples [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], validating input
- validation [Windows Forms], user input
ms.assetid: f1e9c3a0-d0a1-4893-a615-b4b0db046c63
ms.openlocfilehash: 3958089007401d2e977c9c96f07c9196e6216596
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728300"
---
# <a name="how-to-validate-input-with-the-windows-forms-datagrid-control"></a>Cómo: Validar los datos introducidos con el control DataGrid de formularios Windows Forms

> [!NOTE]
> El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).

Hay dos tipos de validación de entrada disponibles para el control Windows Forms <xref:System.Windows.Forms.DataGrid>. Si el usuario intenta especificar un valor que es de un tipo de datos inaceptable para la celda, por ejemplo una cadena en un entero, el nuevo valor no válido se reemplaza por el valor anterior. Este tipo de validación de entrada se realiza automáticamente y no se puede personalizar.

El otro tipo de validación de entrada se puede usar para rechazar cualquier dato inaceptable; por ejemplo, un valor 0 en un campo que debe ser mayor o igual que 1, o una cadena no adecuada. Esto se hace en el conjunto de DataSet escribiendo un controlador de eventos para el evento <xref:System.Data.DataTable.ColumnChanging> o <xref:System.Data.DataTable.RowChanging>. En el ejemplo siguiente se usa el evento <xref:System.Data.DataTable.ColumnChanging> porque no se permite el valor inaceptable para la columna "Product" en particular. Puede usar el evento <xref:System.Data.DataTable.RowChanging> para comprobar que el valor de una columna "fecha de finalización" es posterior a la columna "fecha de inicio" de la misma fila.

## <a name="to-validate-user-input"></a>Para validar la entrada del usuario

1. Escriba código para controlar el evento de <xref:System.Data.DataTable.ColumnChanging> de la tabla adecuada. Cuando se detecten entradas inadecuadas, llame al método <xref:System.Data.DataRow.SetColumnError%2A> del objeto <xref:System.Data.DataRow>.

    ```vb
    Private Sub Customers_ColumnChanging(ByVal sender As Object, _
    ByVal e As System.Data.DataColumnChangeEventArgs)
       ' Only check for errors in the Product column
       If (e.Column.ColumnName.Equals("Product")) Then
          ' Do not allow "Automobile" as a product.
          If CType(e.ProposedValue, String) = "Automobile" Then
             Dim badValue As Object = e.ProposedValue
             e.ProposedValue = "Bad Data"
             e.Row.RowError = "The Product column contains an error"
             e.Row.SetColumnError(e.Column, "Product cannot be " & _
             CType(badValue, String))
          End If
       End If
    End Sub
    ```

    ```csharp
    //Handle column changing events on the Customers table
    private void Customers_ColumnChanging(object sender, System.Data.DataColumnChangeEventArgs e) {

       //Only check for errors in the Product column
       if (e.Column.ColumnName.Equals("Product")) {

          //Do not allow "Automobile" as a product
          if (e.ProposedValue.Equals("Automobile")) {
             object badValue = e.ProposedValue;
             e.ProposedValue = "Bad Data";
             e.Row.RowError = "The Product column contains an error";
             e.Row.SetColumnError(e.Column, "Product cannot be " + badValue);
          }
       }
    }
    ```

2. Conecte el controlador de eventos al evento.

    Coloque el código siguiente en el evento <xref:System.Windows.Forms.Form.Load> del formulario o en su constructor.

    ```vb
    ' Assumes the grid is bound to a dataset called customersDataSet1
    ' with a table called Customers.
    ' Put this code in the form's Load event or its constructor.
    AddHandler customersDataSet1.Tables("Customers").ColumnChanging, AddressOf Customers_ColumnChanging
    ```

    ```csharp
    // Assumes the grid is bound to a dataset called customersDataSet1
    // with a table called Customers.
    // Put this code in the form's Load event or its constructor.
    customersDataSet1.Tables["Customers"].ColumnChanging += new DataColumnChangeEventHandler(this.Customers_ColumnChanging);
    ```

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DataGrid>
- <xref:System.Data.DataTable.ColumnChanging>
- <xref:System.Data.DataRow.SetColumnError%2A>
- [DataGrid (control)](datagrid-control-windows-forms.md)
