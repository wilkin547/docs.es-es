---
title: Filtrar para enlazar el control DataGrid de formularios Windows Forms a un origen de datos
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
ms.openlocfilehash: 920a93894cc126f85bc6b618efbe6e9cedea4881
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59332578"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a>Filtrar para enlazar el control DataGrid de formularios Windows Forms a un origen de datos
> [!NOTE]
>  El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 Los formularios de Windows <xref:System.Windows.Forms.DataGrid> control está diseñado específicamente para mostrar información de un origen de datos. Enlazar el control en tiempo de ejecución mediante una llamada a la <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método. Aunque se pueden mostrar datos desde una variedad de orígenes de datos, los orígenes más habituales son las vistas de datos y conjuntos de datos.  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a>Para enlazar el control DataGrid mediante programación  
  
1. Escribir código para llenar el conjunto de datos.  
  
     Si el origen de datos es un conjunto de datos o una vista de datos basado en una tabla de conjunto de datos, agregue código al formulario para rellenar el conjunto de datos.  
  
     El código exacto que utilice depende de donde obtiene datos del conjunto de datos. Si el conjunto de datos se rellena directamente desde una base de datos, normalmente se invoca el `Fill` método de un adaptador de datos, como se muestra en el ejemplo siguiente, que rellena un conjunto de datos denominado `DsCategories1`:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     Si se llena el conjunto de datos desde un servicio Web XML, normalmente se crea una instancia del servicio en el código y, a continuación, llame a uno de sus métodos devuelvan un conjunto de datos. A continuación, combina el conjunto de datos desde el servicio Web XML en el conjunto de datos local. El ejemplo siguiente muestra cómo puede crear una instancia de un servicio Web XML denominado `CategoriesService`, llame a su `GetCategories` método y mezcla el conjunto de datos resultante en un conjunto de datos local llamado `DsCategories1`:  
  
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
  
2. Llame a la <xref:System.Windows.Forms.DataGrid> del control <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método y pásele el origen de datos y un miembro de datos. Si no es necesario pasar explícitamente un miembro de datos, pase una cadena vacía.  
  
    > [!NOTE]
    >  Si va a enlazar la cuadrícula por primera vez, puede establecer el control <xref:System.Windows.Forms.DataGrid.DataSource%2A> y <xref:System.Windows.Forms.DataGrid.DataMember%2A> propiedades. Sin embargo, no se puede restablecer estas propiedades una vez que se han establecido. Por lo tanto, se recomienda usar siempre el <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método.  
  
     El ejemplo siguiente muestra cómo se puede enlazar mediante programación a la tabla Customers en un conjunto de datos denominado `DsCustomers1`:  
  
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
  
3. (Opcional) Agregar los estilos de tabla adecuada y estilos de columna a la cuadrícula. Si no hay ningún estilo de tabla, verá la tabla, pero con un formato mínimo y con todas las columnas visibles.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre el control DataGrid](datagrid-control-overview-windows-forms.md)
- [Filtrar para agregar tablas y columnas al control DataGrid de Windows Forms](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [Control DataGrid](datagrid-control-windows-forms.md)
- [Enlace de datos en Windows Forms](../windows-forms-data-binding.md)
