---
title: 'Cómo: crear listas principal-detalle con el Control DataGrid de formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 20388c6a-94f9-4d96-be18-8c200491247f
ms.openlocfilehash: 528d07b766987bdeca22ce480c601a2bdd324c89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531123"
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a>Cómo: Crear listas principal-detalle con el control DataGrid de Windows Forms
> [!NOTE]
>  El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 Si su <xref:System.Data.DataSet> contiene una serie de tablas relacionadas, puede utilizar dos <xref:System.Windows.Forms.DataGrid> controles para mostrar los datos en un formato principal-detalle. Una <xref:System.Windows.Forms.DataGrid> está designado como la cuadrícula principal, y el segundo está designado como la cuadrícula de detalles. Cuando se selecciona una entrada en la lista maestra, todas las entradas secundarias relacionadas aparecen en la lista de detalles. Por ejemplo, si su <xref:System.Data.DataSet> contiene una tabla Customers y una tabla relacionada Orders, se especificaría la tabla Customers como cuadrícula principal y la tabla Orders como cuadrícula de detalles. Cuando se selecciona un cliente en la cuadrícula principal, se mostraría todos los pedidos asociados a ese cliente en la tabla Orders en la cuadrícula de detalles.  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a>Para establecer una relación principal-detalle mediante programación  
  
1.  Cree dos nuevos <xref:System.Windows.Forms.DataGrid> controla y establecer sus propiedades.  
  
2.  Agregar tablas al conjunto de datos.  
  
3.  Declare una variable de tipo <xref:System.Data.DataRelation> para representar la relación que desea crear.  
  
4.  Crear una instancia de la relación especificando un nombre para la relación y la tabla, la columna y el elemento que se asociará a las dos tablas.  
  
5.  Agregar la relación con el <xref:System.Data.DataSet> del objeto <xref:System.Data.DataSet.Relations%2A> colección.  
  
6.  Use la <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método de la <xref:System.Windows.Forms.DataGrid> para enlazar cada una de las cuadrículas en el <xref:System.Data.DataSet>.  
  
     En el ejemplo siguiente se muestra cómo establecer una relación principal-detalle entre las tablas Customers y Orders en generado anteriormente <xref:System.Data.DataSet> (`ds`).  
  
    ```vb  
    Dim myDataRelation As DataRelation  
    myDataRelation = New DataRelation _  
       ("CustOrd", ds.Tables("Customers").Columns("CustomerID"), _  
       ds.Tables("Orders").Columns("CustomerID"))  
    ' Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation)  
    GridOrders.SetDataBinding(ds, "Customers")  
    GridDetails.SetDataBinding(ds, "Customers.CustOrd")  
    ```  
  
    ```csharp  
    DataRelation myDataRelation;  
    myDataRelation = new DataRelation("CustOrd", ds.Tables["Customers"].Columns["CustomerID"], ds.Tables["Orders"].Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation);  
    GridOrders.SetDataBinding(ds,"Customers");  
    GridDetails.SetDataBinding(ds,"Customers.CustOrd");  
    ```  
  
    ```cpp  
    DataRelation^ myDataRelation;  
    myDataRelation = gcnew DataRelation("CustOrd",  
       ds->Tables["Customers"]->Columns["CustomerID"],  
       ds->Tables["Orders"]->Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds->Relations->Add(myDataRelation);  
    GridOrders->SetDataBinding(ds, "Customers");  
    GridDetails->SetDataBinding(ds, "Customers.CustOrd");  
    ```  
  
## <a name="see-also"></a>Vea también  
 [DataGrid (control)](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Información general del control DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [Cómo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
