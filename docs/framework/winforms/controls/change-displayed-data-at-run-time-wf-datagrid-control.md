---
title: Procedimiento para cambiar los datos mostrados en tiempo de ejecución en el control DataGrid de formularios Windows Forms
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
ms.openlocfilehash: c7bf70a67729744f4cf96318f6b270a5ea81b812
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917726"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a>Procedimiento para cambiar los datos mostrados en tiempo de ejecución en el control DataGrid de formularios Windows Forms
> [!NOTE]
> El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 Después de crear un Windows Forms <xref:System.Windows.Forms.DataGrid> mediante las características en tiempo de diseño, puede que también desee cambiar dinámicamente los elementos <xref:System.Data.DataSet> del objeto de la cuadrícula en tiempo de ejecución. Esto puede incluir cambios en los valores individuales de la tabla o en el origen de datos que se enlaza <xref:System.Windows.Forms.DataGrid> al control. Los cambios en los valores individuales se realizan <xref:System.Data.DataSet> a través del objeto <xref:System.Windows.Forms.DataGrid> , no del control.  
  
### <a name="to-change-data-programmatically"></a>Para cambiar los datos mediante programación  
  
1. Especifique la tabla deseada del <xref:System.Data.DataSet> objeto y la fila y el campo deseados de la tabla y establezca la celda igual al nuevo valor.  
  
    > [!NOTE]
    > Para especificar la primera tabla de <xref:System.Data.DataSet> la o de la primera fila de la tabla, use 0.  
  
     En el ejemplo siguiente se muestra cómo cambiar la segunda entrada de la primera fila de la primera tabla de un conjunto de `Button1`filas haciendo clic en. Las <xref:System.Data.DataSet> tablas`ds`() y (`0` y `1`) se crearon previamente.  
  
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
  
     (Visual C#, visual C++) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     En tiempo de ejecución, puede utilizar <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> el método para enlazar el <xref:System.Windows.Forms.DataGrid> control a un origen de datos diferente. Por ejemplo, puede tener varios controles de datos ADO.NET, cada uno conectado a una base de datos diferente.  
  
### <a name="to-change-the-datasource-programmatically"></a>Para cambiar el origen de los código mediante programación  
  
1. Establezca el <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método en el nombre del origen de datos y la tabla a la que desea enlazar.  
  
     En el ejemplo siguiente se muestra cómo cambiar el origen de fecha <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> mediante el método a un control de datos ADO.net (adoPubsAuthors) que está conectado a la tabla authors en la base de datos pubs.  
  
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
- [Cómo: Eliminar u ocultar columnas en el control DataGrid de Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [Cómo: Enlazar el control DataGrid de Windows Forms a un origen de datos](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
