---
title: Crear listas principal-detalle con el control DataGrid
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
ms.openlocfilehash: e8ab63d52d97a8a6e6f60da741186e3937350e1e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76730989"
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a>Cómo: Crear listas principal-detalle con el control DataGrid de Windows Forms
> [!NOTE]
> El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Si el <xref:System.Data.DataSet> contiene una serie de tablas relacionadas, puede usar dos controles <xref:System.Windows.Forms.DataGrid> para mostrar los datos en un formato principal/detalle. Una <xref:System.Windows.Forms.DataGrid> se designa como cuadrícula maestra y la segunda se designa como cuadrícula de detalles. Al seleccionar una entrada en la lista maestra, todas las entradas secundarias relacionadas se muestran en la lista de detalles. Por ejemplo, si el <xref:System.Data.DataSet> contiene una tabla Customers y una tabla Orders relacionada, debe especificar la tabla Customers como cuadrícula maestra y la tabla Orders como cuadrícula de detalles. Cuando se selecciona un cliente en la cuadrícula maestra, todos los pedidos asociados a ese cliente en la tabla Orders se mostrarán en la cuadrícula detalles.  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a>Para establecer una relación principal-detalle mediante programación  
  
1. Cree dos nuevos controles de <xref:System.Windows.Forms.DataGrid> y establezca sus propiedades.  
  
2. Agregar tablas al conjunto de DataSet.  
  
3. Declare una variable de tipo <xref:System.Data.DataRelation> para representar la relación que desea crear.  
  
4. Cree una instancia de la relación especificando un nombre para la relación y especificando la tabla, la columna y el elemento que vinculará las dos tablas.  
  
5. Agregue la relación a la colección de <xref:System.Data.DataSet.Relations%2A> del objeto de <xref:System.Data.DataSet>.  
  
6. Utilice el método <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> del <xref:System.Windows.Forms.DataGrid> para enlazar cada una de las cuadrículas a la <xref:System.Data.DataSet>.  
  
     En el ejemplo siguiente se muestra cómo establecer una relación principal-detalle entre las tablas Customers y Orders en una <xref:System.Data.DataSet> generada previamente (`ds`).  
  
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

- [DataGrid (control)](datagrid-control-windows-forms.md)
- [Información general del control DataGrid](datagrid-control-overview-windows-forms.md)
- [Cómo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
