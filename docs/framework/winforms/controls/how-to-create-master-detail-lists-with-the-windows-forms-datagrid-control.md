---
title: Procedimiento Crear listas principal-detalle con el Control DataGrid de Windows Forms
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
ms.openlocfilehash: 6ff13264709c4557d698435ac05b7759be58f1e8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712897"
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a>Procedimiento Crear listas principal-detalle con el Control DataGrid de Windows Forms
> [!NOTE]
>  El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 Si su <xref:System.Data.DataSet> contiene una serie de tablas relacionadas, puede utilizar dos <xref:System.Windows.Forms.DataGrid> controles para mostrar los datos en un formato de maestro y detalles. Una <xref:System.Windows.Forms.DataGrid> se designa como la cuadrícula principal, y el segundo se designa como la cuadrícula de detalles. Cuando se selecciona una entrada en la lista maestra, todas las entradas secundarias relacionadas aparecen en la lista de detalles. Por ejemplo, si su <xref:System.Data.DataSet> contiene una tabla Customers y una tabla de pedidos relacionada, debe especificar la tabla de clientes para la cuadrícula principal y la tabla Orders y cuadrícula de detalles. Cuando se selecciona un cliente en la cuadrícula principal, todos los pedidos asociados a ese cliente en la tabla Orders se mostraría en la cuadrícula de detalles.  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a>Para establecer una relación principal-detalle mediante programación  
  
1.  Cree dos nuevos <xref:System.Windows.Forms.DataGrid> controla y establecer sus propiedades.  
  
2.  Agregar tablas al conjunto de datos.  
  
3.  Declarar una variable de tipo <xref:System.Data.DataRelation> para representar la relación que desea crear.  
  
4.  Crear una instancia de la relación especificando un nombre para la relación y especificando la tabla, la columna y el elemento que se asociará a las dos tablas.  
  
5.  Agregar la relación con el <xref:System.Data.DataSet> del objeto <xref:System.Data.DataSet.Relations%2A> colección.  
  
6.  Use la <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método de la <xref:System.Windows.Forms.DataGrid> para cada una de las cuadrículas para enlazar la <xref:System.Data.DataSet>.  
  
     El ejemplo siguiente muestra cómo establecer una relación principal-detalle entre las tablas Customers y Orders en generado anteriormente <xref:System.Data.DataSet> (`ds`).  
  
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
- [DataGrid (control)](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
- [Información general del control DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)
- [Cómo: Enlazar el Control DataGrid de Windows Forms a un origen de datos](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
