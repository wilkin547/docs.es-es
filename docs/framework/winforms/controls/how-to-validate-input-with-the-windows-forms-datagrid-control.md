---
title: "C&#243;mo: Validar los datos introducidos con el control DataGrid de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "DataGrid (control) [Windows Forms], ejemplos"
  - "DataGrid (control) [Windows Forms], validar los datos introducidos"
  - "ejemplos [Windows Forms], DataGrid (control)"
  - "datos proporcionados por el usuario, validar"
  - "validación, datos proporcionados por el usuario"
ms.assetid: f1e9c3a0-d0a1-4893-a615-b4b0db046c63
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Validar los datos introducidos con el control DataGrid de formularios Windows Forms
> [!NOTE]
>  Aunque el control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>, este control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y, en su caso, de uso futuro.  Para obtener más información, vea [Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Existen dos formas de validar los datos introducidos para el control <xref:System.Windows.Forms.DataGrid> de formularios Windows Forms.  Si el usuario intenta introducir un valor cuyo tipo de datos no es aceptable para la celda, por ejemplo, una cadena en un entero, el nuevo valor no válido se reemplaza con el valor anterior.  Esta clase de validación de los datos introducidos se realiza automáticamente y no se puede personalizar.  
  
 La otra forma de validar los datos introducidos puede utilizarse para rechazar todos los datos que no sean aceptables, por ejemplo un valor 0 en un campo cuyo valor debe ser mayor o igual que 1, o una cadena incorrecta.  Para ello, en el conjunto de datos se escribe un controlador de eventos para el evento <xref:System.Data.DataTable.ColumnChanging> o <xref:System.Data.DataTable.RowChanging>.  En el ejemplo siguiente se utiliza el evento <xref:System.Data.DataTable.ColumnChanging> porque el valor que no es aceptable no se permite en la columna "Product" concretamente.  Se podría utilizar el evento <xref:System.Data.DataTable.RowChanging> para comprobar si el valor de una columna "End Date" es posterior al valor de la columna "Start Date" de la misma fila.  
  
### Para validar los datos introducidos por el usuario  
  
1.  Escriba código que controle el evento <xref:System.Data.DataTable.ColumnChanging> para la tabla correspondiente.  Cuando se detecte una entrada incorrecta, llame al método <xref:System.Data.DataRow.SetColumnError%2A> del objeto <xref:System.Data.DataRow>.  
  
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
  
2.  Conecte el controlador de eventos al evento.  
  
     Incluya el siguiente código en el evento <xref:System.Windows.Forms.Form.Load> del formulario o en su constructor.  
  
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
  
## Vea también  
 <xref:System.Windows.Forms.DataGrid>   
 <xref:System.Data.DataTable.ColumnChanging>   
 <xref:System.Data.DataRow.SetColumnError%2A>   
 [Control DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)