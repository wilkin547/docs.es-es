---
title: Cambiar los datos mostrados en tiempo de ejecución en DataGrid Control
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
ms.openlocfilehash: 6b788c10784082a0c74ee09f8cd85d540c670b84
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142386"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a>Cómo: Cambiar los datos mostrados en tiempo de ejecución en el control DataGrid de formularios Windows Forms
> [!NOTE]
> El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Después de crear <xref:System.Windows.Forms.DataGrid> un formulario Windows Forms con las características en tiempo de <xref:System.Data.DataSet> diseño, es posible que también desee cambiar dinámicamente los elementos del objeto de la cuadrícula en tiempo de ejecución. Esto puede incluir cambios en los valores individuales de <xref:System.Windows.Forms.DataGrid> la tabla o cambiar el origen de datos que está enlazado al control. Los cambios en los <xref:System.Data.DataSet> valores individuales se realizan a través del objeto, no del <xref:System.Windows.Forms.DataGrid> control.  
  
### <a name="to-change-data-programmatically"></a>Para cambiar los datos mediante programación  
  
1. Especifique la tabla <xref:System.Data.DataSet> deseada del objeto y la fila y el campo deseados de la tabla y establezca la celda igual al nuevo valor.  
  
    > [!NOTE]
    > Para especificar la primera <xref:System.Data.DataSet> tabla de la o la primera fila de la tabla, utilice 0.  
  
     En el ejemplo siguiente se muestra cómo cambiar la segunda entrada de `Button1`la primera fila de la primera tabla de un conjunto de datos haciendo clic en . Se <xref:System.Data.DataSet> `ds`crearon anteriormente las tablas ( y ) (`0` y `1`).  
  
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
  
     (Visual C, Visual C++) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     En tiempo de ejecución, puede usar el <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método para enlazar el <xref:System.Windows.Forms.DataGrid> control a un origen de datos diferente. Por ejemplo, puede tener varios controles de datos ADO.NET, cada uno conectado a una base de datos diferente.  
  
### <a name="to-change-the-datasource-programmatically"></a>Para cambiar el DataSource mediante programación  
  
1. Establezca <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> el método en el nombre del origen de datos y la tabla a la que desea enlazar.  
  
     En el ejemplo siguiente se muestra <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> cómo cambiar el origen de fecha mediante el método a un ADO.NET control de datos (adoPubsAuthors) que está conectado a la authors tabla en el Pubs base de datos.  
  
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
  
## <a name="see-also"></a>Consulte también

- [Objetos DataSet de ADO.NET](../../data/adonet/ado-net-datasets.md)
- [Cómo: Eliminar u ocultar columnas del control DataGrid de formularios Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [Cómo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
