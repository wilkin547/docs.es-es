---
title: Filtrar Cambiar los datos mostrados en tiempo de ejecución en el Control DataGrid de Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DataGrid control [Windows Forms], dynamically changing at run time
- DataGrid control [Windows Forms], data binding
- cells [Windows Forms], changing DataGrid cell values
ms.assetid: 0c7a6d00-30de-416e-8223-0a81ddb4c1f8
ms.openlocfilehash: 3ba23dd3966591777c7e354f79dd45ec4530955a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714962"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a>Filtrar Cambiar los datos mostrados en tiempo de ejecución en el Control DataGrid de Windows Forms
> [!NOTE]
>  El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 Después de haber creado un formulario Windows Forms <xref:System.Windows.Forms.DataGrid> con las características de tiempo de diseño, es posible que también desee cambiar dinámicamente los elementos de la <xref:System.Data.DataSet> objeto de la cuadrícula en tiempo de ejecución. Esto puede incluir los cambios realizados en valores individuales de la tabla o cambiar el origen de datos se enlaza a la <xref:System.Windows.Forms.DataGrid> control. Los cambios realizados en los valores individuales se realizan a través de la <xref:System.Data.DataSet> objeto, no el <xref:System.Windows.Forms.DataGrid> control.  
  
### <a name="to-change-data-programmatically"></a>Para cambiar datos mediante programación  
  
1.  Especifique la tabla deseada desde la <xref:System.Data.DataSet> objeto y la fila y el campo de la tabla y establece la celda igual que el nuevo valor deseado.  
  
    > [!NOTE]
    >  Para especificar la primera tabla de la <xref:System.Data.DataSet> o la primera fila de la tabla, utilice 0.  
  
     El ejemplo siguiente muestra cómo cambiar la segunda entrada de la primera fila de la primera tabla de un conjunto de datos, haga clic en `Button1`. El <xref:System.Data.DataSet> (`ds`) y las tablas (`0` y `1`) fueron creados previamente.  
  
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
  
     En puede usar el tiempo de ejecución el <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método para enlazar el <xref:System.Windows.Forms.DataGrid> control a un origen de datos diferentes. Por ejemplo, pueden tener varios [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] controles de datos, cada uno conectado a una base de datos diferentes.  
  
### <a name="to-change-the-datasource-programmatically"></a>Para cambiar el origen de datos mediante programación  
  
1.  Establecer el <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método en el nombre del origen de datos y la tabla que desea enlazar a.  
  
     El ejemplo siguiente muestra cómo cambiar el origen de fecha mediante el <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método a un [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] control de datos (adoPubsAuthors) que está conectado a la tabla Authors de la base de datos Pubs.  
  
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
- [Objetos DataSet de ADO.NET](../../data/adonet/ado-net-datasets.md)
- [Cómo: Eliminar u ocultar columnas en el Control DataGrid de Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [Cómo: Agregar tablas y columnas al Control DataGrid de formularios Windows Forms](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [Cómo: Enlazar el Control DataGrid de Windows Forms a un origen de datos](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
