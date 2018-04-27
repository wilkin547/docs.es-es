---
title: 'Cómo: Cambiar los datos mostrados en tiempo de ejecución en el control DataGrid de formularios Windows Forms'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DataGrid control [Windows Forms], dynamically changing at run time
- DataGrid control [Windows Forms], data binding
- cells [Windows Forms], changing DataGrid cell values
ms.assetid: 0c7a6d00-30de-416e-8223-0a81ddb4c1f8
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ea90c3532203a61beded5eceeee5cf535a74b87b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a>Cómo: Cambiar los datos mostrados en tiempo de ejecución en el control DataGrid de formularios Windows Forms
> [!NOTE]
>  El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 Después de haber creado un formulario Windows Forms <xref:System.Windows.Forms.DataGrid> con las características de tiempo de diseño, puede que también desee cambiar dinámicamente los elementos de la <xref:System.Data.DataSet> objeto de la cuadrícula en tiempo de ejecución. Esto puede incluir la modificación de valores individuales de la tabla o cambiar el origen de datos se enlaza a la <xref:System.Windows.Forms.DataGrid> control. Cambios en los valores individuales se realizan a través del <xref:System.Data.DataSet> el objeto, no el <xref:System.Windows.Forms.DataGrid> control.  
  
### <a name="to-change-data-programmatically"></a>Para cambiar los datos mediante programación  
  
1.  Especificar la tabla deseada de la <xref:System.Data.DataSet> objeto y la fila y campo de la tabla y establezca la celda en el nuevo valor deseado.  
  
    > [!NOTE]
    >  Para especificar la primera tabla de la <xref:System.Data.DataSet> o la primera fila de la tabla, utilice 0.  
  
     En el ejemplo siguiente se muestra cómo cambiar la segunda entrada de la primera fila de la primera tabla de un conjunto de datos, haga clic en `Button1`. El <xref:System.Data.DataSet> (`ds`) y tablas (`0` y `1`) creadas con anterioridad.  
  
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
  
     (Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     Durante la ejecución puede utilizar el <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método para enlazar el <xref:System.Windows.Forms.DataGrid> control a un origen de datos diferente. Por ejemplo, puede tener varios [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] controles de datos, cada uno conectado a una base de datos diferente.  
  
### <a name="to-change-the-datasource-programmatically"></a>Para cambiar el origen de datos mediante programación  
  
1.  Establecer el <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método en el nombre del origen de datos y la tabla que desea enlazar a.  
  
     En el ejemplo siguiente se muestra cómo cambiar el origen de fecha mediante el <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método a un [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] control de datos (adoPubsAuthors) que está conectado a la tabla Authors de la base de datos Pubs.  
  
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
  
## <a name="see-also"></a>Vea también  
 [Objetos DataSet de ADO.NET](../../../../docs/framework/data/adonet/ado-net-datasets.md)  
 [Cómo: Eliminar u ocultar columnas del control DataGrid de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 [Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 [Cómo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
