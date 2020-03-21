---
title: Enlazar DataGrid Control a un origen de datos
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
ms.openlocfilehash: 42514c6a0ab9cf912a32b13675a069976632ece5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182243"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a>Cómo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos
> [!NOTE]
> El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 El control <xref:System.Windows.Forms.DataGrid> de formularios Windows Forms está diseñado específicamente para mostrar información de un origen de datos. Enlazar el control en tiempo <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> de ejecución mediante una llamada al método. Aunque puede mostrar datos de una variedad de orígenes de datos, los orígenes más típicos son conjuntos de datos y vistas de datos.  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a>Para enlazar a datos el dataGrid control mediante programación  
  
1. Escriba código para rellenar el conjunto de datos.  
  
     Si el origen de datos es un conjunto de datos o una vista de datos basada en una tabla de conjunto de datos, agregue código al formulario para rellenar el conjunto de datos.  
  
     El código exacto que utilice depende de dónde el conjunto de datos obtiene datos. Si el conjunto de datos se rellena directamente `Fill` desde una base de datos, normalmente se llama `DsCategories1`al método de un adaptador de datos, como en el ejemplo siguiente, que rellena un conjunto de datos denominado:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     Si el conjunto de datos se rellena desde un servicio Web XML, normalmente se crea una instancia del servicio en el código y, a continuación, se llama a uno de sus métodos para devolver un conjunto de datos. A continuación, combine el conjunto de datos del servicio Web XML en el conjunto de datos local. En el ejemplo siguiente se muestra cómo crear `CategoriesService`una instancia `GetCategories` de un servicio Web XML denominado `DsCategories1`, llamar a su método y combinar el conjunto de datos resultante en un conjunto de datos local denominado:  
  
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
  
2. Llame <xref:System.Windows.Forms.DataGrid> al método <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> del control, pasándole el origen de datos y un miembro de datos. Si no necesita pasar explícitamente un miembro de datos, pase una cadena vacía.  
  
    > [!NOTE]
    > Si va a enlazar la cuadrícula por primera vez, <xref:System.Windows.Forms.DataGrid.DataSource%2A> <xref:System.Windows.Forms.DataGrid.DataMember%2A> puede establecer las propiedades y el control. Sin embargo, no puede restablecer estas propiedades una vez que se han establecido. Por lo tanto, se recomienda <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> que siempre utilice el método.  
  
     En el ejemplo siguiente se muestra cómo se puede `DsCustomers1`enlazar mediante programación a la tabla Customers de un conjunto de datos denominado:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     Si la tabla Customers es la única tabla del conjunto de datos, también puede enlazar la cuadrícula de esta manera:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3. (Opcional) Agregue los estilos de tabla y los estilos de columna adecuados a la cuadrícula. Si no hay estilos de tabla, verá la tabla, pero con un formato mínimo y con todas las columnas visibles.  
  
## <a name="see-also"></a>Consulte también

- [Información general del control DataGrid](datagrid-control-overview-windows-forms.md)
- [Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [DataGrid (control)](datagrid-control-windows-forms.md)
- [Enlace de datos en Windows Forms](../windows-forms-data-binding.md)
