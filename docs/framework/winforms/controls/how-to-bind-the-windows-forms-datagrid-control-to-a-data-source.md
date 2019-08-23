---
title: Procedimiento para enlazar el control DataGrid de formularios Windows Forms a un origen de datos
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
ms.openlocfilehash: bac24c2dd622ea780408e902d08708ac09561044
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922724"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a>Procedimiento para enlazar el control DataGrid de formularios Windows Forms a un origen de datos
> [!NOTE]
> El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 El control <xref:System.Windows.Forms.DataGrid> Windows Forms está diseñado específicamente para mostrar información de un origen de datos. Para enlazar el control en tiempo de ejecución, <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> llame al método. Aunque puede mostrar los datos de diversos orígenes de datos, los orígenes más habituales son los conjuntos de datos y las vistas de datos.  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a>Para enlazar datos mediante programación al control DataGrid  
  
1. Escriba código para rellenar el conjunto de DataSet.  
  
     Si el origen de datos es un conjunto de datos o una vista de datos basada en una tabla de conjunto de datos, agregue código al formulario para rellenar el conjunto de datos.  
  
     El código exacto que se utiliza depende de la ubicación del conjunto de datos. Si el conjunto de datos se rellena directamente desde una base de datos, normalmente `Fill` se llama al método de un adaptador de datos, como en el ejemplo siguiente, que rellena `DsCategories1`un conjunto de datos denominado:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     Si el conjunto de resultados se rellena desde un servicio Web XML, normalmente se crea una instancia del servicio en el código y, a continuación, se llama a uno de sus métodos para devolver un conjunto de resultados. A continuación, combine el conjunto de DataSet del servicio Web XML en el conjunto de DataSet local. En el ejemplo siguiente se muestra cómo se puede crear una instancia de un servicio Web `CategoriesService`XML denominado, `GetCategories` llamar a su método y combinar el conjunto de resultados en un `DsCategories1`conjunto de elementos local denominado:  
  
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
  
2. Llame al método del <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> control,pasándoleelorigendedatosyunmiembrodedatos.<xref:System.Windows.Forms.DataGrid> Si no necesita pasar explícitamente un miembro de datos, pase una cadena vacía.  
  
    > [!NOTE]
    > Si enlaza la cuadrícula por primera vez, puede establecer las propiedades y <xref:System.Windows.Forms.DataGrid.DataSource%2A> <xref:System.Windows.Forms.DataGrid.DataMember%2A> del control. Sin embargo, no puede restablecer estas propiedades una vez que se han establecido. Por lo tanto, se recomienda usar siempre el <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método.  
  
     En el ejemplo siguiente se muestra cómo se puede enlazar mediante programación a la tabla Customers `DsCustomers1`en un conjunto de una llamada:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     Si la tabla Customers es la única tabla del conjunto de elementos, puede enlazar la cuadrícula como alternativa de esta manera:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3. Opta Agregue los estilos de tabla y de columna correspondientes a la cuadrícula. Si no hay ningún estilo de tabla, verá la tabla, pero con el formato mínimo y con todas las columnas visibles.  
  
## <a name="see-also"></a>Vea también

- [Información general del control DataGrid](datagrid-control-overview-windows-forms.md)
- [Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [DataGrid (control)](datagrid-control-windows-forms.md)
- [Enlace de datos en Windows Forms](../windows-forms-data-binding.md)
