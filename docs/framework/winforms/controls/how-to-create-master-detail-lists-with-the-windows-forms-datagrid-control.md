---
title: Procedimiento Crear listas principal-detalle con el control DataGrid Windows Forms
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
ms.openlocfilehash: f0fd95cf0cd66e9a5105c0b8ff77d8c536a5822d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914762"
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a>Procedimiento para crear listas maestro y detalle con el control DataGrid de formularios Windows Forms
> [!NOTE]
> El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 Si contiene una serie de tablas relacionadas, puede usar dos <xref:System.Windows.Forms.DataGrid> controles para mostrar los datos en un formato principal/detalle. <xref:System.Data.DataSet> Uno <xref:System.Windows.Forms.DataGrid> se designa como la cuadrícula maestra y el segundo se designa como la cuadrícula de detalles. Al seleccionar una entrada en la lista maestra, todas las entradas secundarias relacionadas se muestran en la lista de detalles. Por ejemplo, si <xref:System.Data.DataSet> contiene una tabla Customers y una tabla Orders relacionada, debe especificar la tabla Customers como cuadrícula maestra y la tabla Orders como cuadrícula de detalles. Cuando se selecciona un cliente en la cuadrícula maestra, todos los pedidos asociados a ese cliente en la tabla Orders se mostrarán en la cuadrícula detalles.  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a>Para establecer una relación principal-detalle mediante programación  
  
1. Cree dos nuevos <xref:System.Windows.Forms.DataGrid> controles y establezca sus propiedades.  
  
2. Agregar tablas al conjunto de DataSet.  
  
3. Declare una variable de <xref:System.Data.DataRelation> tipo para representar la relación que desea crear.  
  
4. Cree una instancia de la relación especificando un nombre para la relación y especificando la tabla, la columna y el elemento que vinculará las dos tablas.  
  
5. Agregue la relación a la <xref:System.Data.DataSet> colección del <xref:System.Data.DataSet.Relations%2A> objeto.  
  
6. Utilice el <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método <xref:System.Windows.Forms.DataGrid> de para enlazar cada una de <xref:System.Data.DataSet>las cuadrículas a.  
  
     En el ejemplo siguiente se muestra cómo establecer una relación principal-detalle entre las tablas Customers y Orders de <xref:System.Data.DataSet> un`ds`generado previamente ().  
  
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
- [Procedimientos: Enlazar el control DataGrid de Windows Forms a un origen de datos](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
