---
title: 'Cómo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- bound controls [Windows Forms], DataGrid control
- Windows Forms controls, data binding
- bound controls [Windows Forms]
- data-bound controls [Windows Forms], DataGrid
ms.assetid: 128cdb07-dfd3-4d60-9d6a-902847667c36
ms.openlocfilehash: 62f61eb2d294baf007b0b3f749f3cf6b7f4857c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a>Cómo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos
> [!NOTE]
>  El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 Los formularios Windows Forms <xref:System.Windows.Forms.DataGrid> control está diseñado específicamente para mostrar información de un origen de datos. Enlazar el control en tiempo de ejecución mediante una llamada a la <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método. Aunque se pueden mostrar datos desde una variedad de orígenes de datos, los orígenes más habituales son vistas de datos y conjuntos de datos.  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a>Para enlazar el control DataGrid mediante programación  
  
1.  Escribir código para llenar el conjunto de datos.  
  
     Si el origen de datos es un conjunto de datos o una vista de datos basada en una tabla de conjunto de datos, agregue código al formulario para rellenar el conjunto de datos.  
  
     El código exacto que utilice depende de que el conjunto de datos está obteniendo datos. Si se está llenando el conjunto de datos directamente desde una base de datos, normalmente se invoca el `Fill` método de un adaptador de datos, como se muestra en el ejemplo siguiente, que rellena un conjunto de datos denominado `DsCategories1`:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     Si se llena el conjunto de datos de un servicio Web XML, normalmente se crea una instancia del servicio en el código y, a continuación, llame a uno de sus métodos para devolver un conjunto de datos. A continuación, combina el conjunto de datos desde el servicio Web XML en el conjunto de datos local. En el ejemplo siguiente se muestra cómo puede crear una instancia de un servicio Web XML denominado `CategoriesService`, llame a su `GetCategories` método y mezcla el conjunto de datos resultante en un conjunto de datos local denominado `DsCategories1`:  
  
    ```vb  
    Dim ws As New MyProject.localhost.CategoriesService()  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials  
    DsCategories1.Merge(ws.GetCategories())  
    ```  
  
    ```csharp  
    MyProject.localhost.CategoriesService ws = new MyProject.localhost.CategoriesService();  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials;  
    DsCategories1.Merge(ws.GetCategories());  
    ```  
  
    ```cpp  
    MyProject::localhost::CategoriesService^ ws =   
       new MyProject::localhost::CategoriesService();  
    ws->Credentials = System::Net::CredentialCache::DefaultCredentials;  
    dsCategories1->Merge(ws->GetCategories());  
    ```  
  
2.  Llame a la <xref:System.Windows.Forms.DataGrid> del control <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método y pásele el origen de datos y un miembro de datos. Si no necesita pasar explícitamente un miembro de datos, pase una cadena vacía.  
  
    > [!NOTE]
    >  Si va a enlazar la cuadrícula por primera vez, puede establecer el control <xref:System.Windows.Forms.DataGrid.DataSource%2A> y <xref:System.Windows.Forms.DataGrid.DataMember%2A> propiedades. Sin embargo, no se puede restablecer estas propiedades una vez que se han establecido. Por lo tanto, se recomienda usar siempre el <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método.  
  
     En el ejemplo siguiente se muestra cómo se puede enlazar mediante programación a la tabla Customers de un conjunto de datos denominado `DsCustomers1`:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     Si la tabla Customers es la única tabla en el conjunto de datos, también puede enlazar la cuadrícula de esta manera:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3.  (Opcional) Agregar los estilos de tabla adecuado y estilos de columna a la cuadrícula. Si no hay ningún estilo de tabla, verá la tabla, pero con un formato mínimo y con todas las columnas visibles.  
  
## <a name="see-also"></a>Vea también  
 [Información general del control DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 [DataGrid (control)](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Enlace de datos en Windows Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md)
