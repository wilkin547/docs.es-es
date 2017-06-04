---
title: "C&#243;mo: Cambiar los datos mostrados en tiempo de ejecuci&#243;n en el control DataGrid de formularios Windows Forms | Microsoft Docs"
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
  - "celdas, cambiar valores de celda de DataGrid"
  - "DataGrid (control) [Windows Forms], enlace de datos"
  - "DataGrid (control) [Windows Forms], cambiar dinámicamente en tiempo de ejecución"
ms.assetid: 0c7a6d00-30de-416e-8223-0a81ddb4c1f8
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Cambiar los datos mostrados en tiempo de ejecuci&#243;n en el control DataGrid de formularios Windows Forms
> [!NOTE]
>  Aunque el control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>, este control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y, en su caso, de uso futuro.  Para obtener más información, vea [Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Después de crear un control <xref:System.Windows.Forms.DataGrid> de formularios Windows Forms por medio de las características en tiempo de diseño, es posible que también desee cambiar dinámicamente los elementos del objeto <xref:System.Data.DataSet> de la cuadrícula en tiempo de ejecución.  Esto puede incluir la modificación de valores individuales de la tabla o el cambio del origen de datos al que está enlazado el control <xref:System.Windows.Forms.DataGrid>.  Las modificaciones de valores individuales se realizan mediante el objeto <xref:System.Data.DataSet>, no mediante el control <xref:System.Windows.Forms.DataGrid>.  
  
### Para modificar datos mediante programación  
  
1.  Especifique la tabla que desea del objeto <xref:System.Data.DataSet>, así como la fila y el campo de la tabla, y establezca el nuevo valor en la celda.  
  
    > [!NOTE]
    >  Para especificar la primera tabla del objeto <xref:System.Data.DataSet> o la primera fila de la tabla, utilice 0.  
  
     En el ejemplo siguiente se muestra cómo cambiar la segunda entrada de la primera fila de la primera tabla de un conjunto de datos al hacer clic en `Button1`.  Previamente se creó <xref:System.Data.DataSet> \(`ds`\) y las tablas \(`0` y`1`\).  
  
    ```vb  
    Protected Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       ds.tables(0).rows(0)(1) = "NewEntry"  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       ds.Tables[0].Rows[0][1]="NewEntry";  
    }  
  
    ```  
  
    ```cpp  
    private:   
       void button1_Click(System::Object^ sender, System::EventArgs^ e)  
       {  
          dataSet1->Tables[0]->Rows[0][1] = "NewEntry";  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     En tiempo de ejecución puede utilizar el método <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> para enlazar el control <xref:System.Windows.Forms.DataGrid> a un origen de datos diferente.  Por ejemplo, puede tener varios controles de datos [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], cada uno de ellos conectado a una base de datos diferente.  
  
### Para cambiar el origen de datos mediante programación  
  
1.  Establezca el método <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> en el nombre del origen de datos y de la tabla con los que desea establecer el enlace.  
  
     En el ejemplo siguiente se muestra cómo cambiar el origen de datos mediante el método <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> por un control de datos [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] \(adoPubsAuthors\) conectado a la tabla Authors de la base de datos Pubs.  
  
    ```vb  
    Private Sub ResetSource()  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors")  
    End Sub  
  
    ```  
  
    ```csharp  
    private void ResetSource()  
    {  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors");  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void ResetSource()  
       {  
          dataGrid1->SetDataBinding(adoPubsAuthors, "Authors");  
       }  
    ```  
  
## Vea también  
 [Datasets de ADO.NET](../../../../docs/framework/data/adonet/ado-net-datasets.md)   
 [Cómo: Eliminar u ocultar columnas del control DataGrid de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)   
 [Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)   
 [Cómo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)