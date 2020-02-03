---
title: Enlazar el control DataGrid a un origen de datos
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
ms.openlocfilehash: 2634a6bd8ace36bcf7a49120162474a8c04b2b83
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746692"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a>Cómo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos
> [!NOTE]
> El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 El control <xref:System.Windows.Forms.DataGrid> de Windows Forms está diseñado específicamente para mostrar información de un origen de datos. Puede enlazar el control en tiempo de ejecución llamando al método <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>. Aunque puede mostrar los datos de diversos orígenes de datos, los orígenes más habituales son los conjuntos de datos y las vistas de datos.  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a>Para enlazar datos mediante programación al control DataGrid  
  
1. Escriba código para rellenar el conjunto de DataSet.  
  
     Si el origen de datos es un conjunto de datos o una vista de datos basada en una tabla de conjunto de datos, agregue código al formulario para rellenar el conjunto de datos.  
  
     El código exacto que se utiliza depende de la ubicación del conjunto de datos. Si el conjunto de datos se rellena directamente desde una base de datos, normalmente se llama al método `Fill` de un adaptador de datos, como en el ejemplo siguiente, que rellena un conjunto de datos denominado `DsCategories1`:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     Si el conjunto de resultados se rellena desde un servicio Web XML, normalmente se crea una instancia del servicio en el código y, a continuación, se llama a uno de sus métodos para devolver un conjunto de resultados. A continuación, combine el conjunto de DataSet del servicio Web XML en el conjunto de DataSet local. En el ejemplo siguiente se muestra cómo se puede crear una instancia de un servicio Web XML denominado `CategoriesService`, llamar a su método `GetCategories` y combinar el conjunto de resultados en un conjunto de elementos local denominado `DsCategories1`:  
  
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
  
2. Llame al método <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> del control <xref:System.Windows.Forms.DataGrid>, pasándole el origen de datos y un miembro de datos. Si no necesita pasar explícitamente un miembro de datos, pase una cadena vacía.  
  
    > [!NOTE]
    > Si enlaza la cuadrícula por primera vez, puede establecer las propiedades <xref:System.Windows.Forms.DataGrid.DataSource%2A> y <xref:System.Windows.Forms.DataGrid.DataMember%2A> del control. Sin embargo, no puede restablecer estas propiedades una vez que se han establecido. Por lo tanto, se recomienda usar siempre el método <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>.  
  
     En el ejemplo siguiente se muestra cómo se puede enlazar mediante programación a la tabla Customers en un conjunto de elementos denominado `DsCustomers1`:  
  
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
  
## <a name="see-also"></a>Consulte también

- [Información general del control DataGrid](datagrid-control-overview-windows-forms.md)
- [Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [DataGrid (control)](datagrid-control-windows-forms.md)
- [Enlace de datos en Windows Forms](../windows-forms-data-binding.md)
