---
title: "Cómo: Validar los datos introducidos con el control DataGrid de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f5e0c366f71f602be2bb1508a6abb00d3d0c83ea
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-validate-input-with-the-windows-forms-datagrid-control"></a>Cómo: Validar los datos introducidos con el control DataGrid de formularios Windows Forms
> [!NOTE]
>  El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 Hay dos tipos de validación de entrada disponibles para los formularios Windows Forms <xref:System.Windows.Forms.DataGrid> control. Si el usuario intenta especificar un valor que es un tipo de datos aceptable para la celda, por ejemplo, una cadena en un entero, el nuevo valor no válido se sustituye con el valor antiguo. Este tipo de validación de entrada se realiza automáticamente y no se puede personalizar.  
  
 El otro tipo de validación de entrada puede utilizarse para rechazar los datos aceptables, por ejemplo, un valor 0 en un campo que debe ser mayor o igual que 1, o una cadena incorrecta. Esto se hace en el conjunto de datos mediante la escritura de un controlador de eventos para el <xref:System.Data.DataTable.ColumnChanging> o <xref:System.Data.DataTable.RowChanging> eventos. El ejemplo siguiente utiliza la <xref:System.Data.DataTable.ColumnChanging> evento porque el valor aceptable no se permite en la columna "Product" en particular. Puede usar el <xref:System.Data.DataTable.RowChanging> eventos para comprobar que el valor de una columna "End Date" es posterior a la columna "Start Date" de la misma fila.  
  
### <a name="to-validate-user-input"></a>Para validar la entrada del usuario  
  
1.  Escribir código para controlar la <xref:System.Data.DataTable.ColumnChanging> eventos para la tabla correspondiente. Cuando se detecte una entrada incorrecta, llame a la <xref:System.Data.DataRow.SetColumnError%2A> método de la <xref:System.Data.DataRow> objeto.  
  
    ```vb  
    Private Sub Customers_ColumnChanging(ByVal sender As Object, _  
    ByVal e As System.Data.DataColumnChangeEventArgs)  
       ' Only check for errors in the Product column  
       If (e.Column.ColumnName.Equals("Product")) Then  
          ' Do not allow "Automobile" as a product.  
          If CType(e.ProposedValue, String) = "Automobile" Then  
             Dim badValue As Object = e.ProposedValue  
             e.ProposedValue = "Bad Data"  
             e.Row.RowError = "The Product column contians an error"  
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
  
2.  Conectar el controlador de eventos para el evento.  
  
     Lugar el siguiente código dentro del formulario <xref:System.Windows.Forms.Form.Load> eventos o en su constructor.  
  
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
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGrid>  
 <xref:System.Data.DataTable.ColumnChanging>  
 <xref:System.Data.DataRow.SetColumnError%2A>  
 [DataGrid (control)](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
