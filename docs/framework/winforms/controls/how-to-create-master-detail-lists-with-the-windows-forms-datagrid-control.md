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
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a><span data-ttu-id="9da5f-102">Cómo: Crear listas principal-detalle con el control DataGrid de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9da5f-102">How to: Create Master/Detail Lists with the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="9da5f-103">El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="9da5f-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="9da5f-104">Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).</span><span class="sxs-lookup"><span data-stu-id="9da5f-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="9da5f-105">Si su <xref:System.Data.DataSet> contiene una serie de tablas relacionadas, puede utilizar dos <xref:System.Windows.Forms.DataGrid> controles para mostrar los datos en un formato principal-detalle.</span><span class="sxs-lookup"><span data-stu-id="9da5f-105">If your <xref:System.Data.DataSet> contains a series of related tables, you can use two <xref:System.Windows.Forms.DataGrid> controls to display the data in a master/detail format.</span></span> <span data-ttu-id="9da5f-106">Una <xref:System.Windows.Forms.DataGrid> está designado como la cuadrícula principal, y el segundo está designado como la cuadrícula de detalles.</span><span class="sxs-lookup"><span data-stu-id="9da5f-106">One <xref:System.Windows.Forms.DataGrid> is designated to be the master grid, and the second is designated to be the details grid.</span></span> <span data-ttu-id="9da5f-107">Cuando se selecciona una entrada en la lista maestra, todas las entradas secundarias relacionadas aparecen en la lista de detalles.</span><span class="sxs-lookup"><span data-stu-id="9da5f-107">When you select an entry in the master list, all of the related child entries are shown in the details list.</span></span> <span data-ttu-id="9da5f-108">Por ejemplo, si su <xref:System.Data.DataSet> contiene una tabla Customers y una tabla relacionada Orders, se especificaría la tabla Customers como cuadrícula principal y la tabla Orders como cuadrícula de detalles.</span><span class="sxs-lookup"><span data-stu-id="9da5f-108">For example, if your <xref:System.Data.DataSet> contains a Customers table and a related Orders table, you would specify the Customers table to be the master grid and the Orders table to be the details grid.</span></span> <span data-ttu-id="9da5f-109">Cuando se selecciona un cliente en la cuadrícula principal, se mostraría todos los pedidos asociados a ese cliente en la tabla Orders en la cuadrícula de detalles.</span><span class="sxs-lookup"><span data-stu-id="9da5f-109">When a customer is selected from the master grid, all of the orders associated with that customer in the Orders table would be displayed in the details grid.</span></span>  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a><span data-ttu-id="9da5f-110">Para establecer una relación principal-detalle mediante programación</span><span class="sxs-lookup"><span data-stu-id="9da5f-110">To set a master/detail relationship programmatically</span></span>  
  
1.  <span data-ttu-id="9da5f-111">Cree dos nuevos <xref:System.Windows.Forms.DataGrid> controla y establecer sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="9da5f-111">Create two new <xref:System.Windows.Forms.DataGrid> controls and set their properties.</span></span>  
  
2.  <span data-ttu-id="9da5f-112">Agregar tablas al conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="9da5f-112">Add tables to the dataset.</span></span>  
  
3.  <span data-ttu-id="9da5f-113">Declare una variable de tipo <xref:System.Data.DataRelation> para representar la relación que desea crear.</span><span class="sxs-lookup"><span data-stu-id="9da5f-113">Declare a variable of type <xref:System.Data.DataRelation> to represent the relation you want to create.</span></span>  
  
4.  <span data-ttu-id="9da5f-114">Crear una instancia de la relación especificando un nombre para la relación y la tabla, la columna y el elemento que se asociará a las dos tablas.</span><span class="sxs-lookup"><span data-stu-id="9da5f-114">Instantiate the relationship by specifying a name for the relationship and specifying the table, column, and item that will tie the two tables.</span></span>  
  
5.  <span data-ttu-id="9da5f-115">Agregar la relación con el <xref:System.Data.DataSet> del objeto <xref:System.Data.DataSet.Relations%2A> colección.</span><span class="sxs-lookup"><span data-stu-id="9da5f-115">Add the relationship to the <xref:System.Data.DataSet> object's <xref:System.Data.DataSet.Relations%2A> collection.</span></span>  
  
6.  <span data-ttu-id="9da5f-116">Use la <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método de la <xref:System.Windows.Forms.DataGrid> para enlazar cada una de las cuadrículas en el <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="9da5f-116">Use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method of the <xref:System.Windows.Forms.DataGrid> to bind each of the grids to the <xref:System.Data.DataSet>.</span></span>  
  
     <span data-ttu-id="9da5f-117">En el ejemplo siguiente se muestra cómo establecer una relación principal-detalle entre las tablas Customers y Orders en generado anteriormente <xref:System.Data.DataSet> (`ds`).</span><span class="sxs-lookup"><span data-stu-id="9da5f-117">The following example shows how to set a master/detail relationship between the Customers and Orders tables in a previously generated <xref:System.Data.DataSet> (`ds`).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9da5f-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="9da5f-118">See Also</span></span>  
 [<span data-ttu-id="9da5f-119">DataGrid (control)</span><span class="sxs-lookup"><span data-stu-id="9da5f-119">DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [<span data-ttu-id="9da5f-120">Información general del control DataGrid</span><span class="sxs-lookup"><span data-stu-id="9da5f-120">DataGrid Control Overview</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [<span data-ttu-id="9da5f-121">Cómo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="9da5f-121">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
