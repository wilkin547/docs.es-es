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
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a><span data-ttu-id="c8573-102">Procedimiento para crear listas maestro y detalle con el control DataGrid de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c8573-102">How to: Create Master/Detail Lists with the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="c8573-103">El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="c8573-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="c8573-104">Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).</span><span class="sxs-lookup"><span data-stu-id="c8573-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="c8573-105">Si contiene una serie de tablas relacionadas, puede usar dos <xref:System.Windows.Forms.DataGrid> controles para mostrar los datos en un formato principal/detalle. <xref:System.Data.DataSet></span><span class="sxs-lookup"><span data-stu-id="c8573-105">If your <xref:System.Data.DataSet> contains a series of related tables, you can use two <xref:System.Windows.Forms.DataGrid> controls to display the data in a master/detail format.</span></span> <span data-ttu-id="c8573-106">Uno <xref:System.Windows.Forms.DataGrid> se designa como la cuadrícula maestra y el segundo se designa como la cuadrícula de detalles.</span><span class="sxs-lookup"><span data-stu-id="c8573-106">One <xref:System.Windows.Forms.DataGrid> is designated to be the master grid, and the second is designated to be the details grid.</span></span> <span data-ttu-id="c8573-107">Al seleccionar una entrada en la lista maestra, todas las entradas secundarias relacionadas se muestran en la lista de detalles.</span><span class="sxs-lookup"><span data-stu-id="c8573-107">When you select an entry in the master list, all of the related child entries are shown in the details list.</span></span> <span data-ttu-id="c8573-108">Por ejemplo, si <xref:System.Data.DataSet> contiene una tabla Customers y una tabla Orders relacionada, debe especificar la tabla Customers como cuadrícula maestra y la tabla Orders como cuadrícula de detalles.</span><span class="sxs-lookup"><span data-stu-id="c8573-108">For example, if your <xref:System.Data.DataSet> contains a Customers table and a related Orders table, you would specify the Customers table to be the master grid and the Orders table to be the details grid.</span></span> <span data-ttu-id="c8573-109">Cuando se selecciona un cliente en la cuadrícula maestra, todos los pedidos asociados a ese cliente en la tabla Orders se mostrarán en la cuadrícula detalles.</span><span class="sxs-lookup"><span data-stu-id="c8573-109">When a customer is selected from the master grid, all of the orders associated with that customer in the Orders table would be displayed in the details grid.</span></span>  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a><span data-ttu-id="c8573-110">Para establecer una relación principal-detalle mediante programación</span><span class="sxs-lookup"><span data-stu-id="c8573-110">To set a master/detail relationship programmatically</span></span>  
  
1. <span data-ttu-id="c8573-111">Cree dos nuevos <xref:System.Windows.Forms.DataGrid> controles y establezca sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="c8573-111">Create two new <xref:System.Windows.Forms.DataGrid> controls and set their properties.</span></span>  
  
2. <span data-ttu-id="c8573-112">Agregar tablas al conjunto de DataSet.</span><span class="sxs-lookup"><span data-stu-id="c8573-112">Add tables to the dataset.</span></span>  
  
3. <span data-ttu-id="c8573-113">Declare una variable de <xref:System.Data.DataRelation> tipo para representar la relación que desea crear.</span><span class="sxs-lookup"><span data-stu-id="c8573-113">Declare a variable of type <xref:System.Data.DataRelation> to represent the relation you want to create.</span></span>  
  
4. <span data-ttu-id="c8573-114">Cree una instancia de la relación especificando un nombre para la relación y especificando la tabla, la columna y el elemento que vinculará las dos tablas.</span><span class="sxs-lookup"><span data-stu-id="c8573-114">Instantiate the relationship by specifying a name for the relationship and specifying the table, column, and item that will tie the two tables.</span></span>  
  
5. <span data-ttu-id="c8573-115">Agregue la relación a la <xref:System.Data.DataSet> colección del <xref:System.Data.DataSet.Relations%2A> objeto.</span><span class="sxs-lookup"><span data-stu-id="c8573-115">Add the relationship to the <xref:System.Data.DataSet> object's <xref:System.Data.DataSet.Relations%2A> collection.</span></span>  
  
6. <span data-ttu-id="c8573-116">Utilice el <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método <xref:System.Windows.Forms.DataGrid> de para enlazar cada una de <xref:System.Data.DataSet>las cuadrículas a.</span><span class="sxs-lookup"><span data-stu-id="c8573-116">Use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method of the <xref:System.Windows.Forms.DataGrid> to bind each of the grids to the <xref:System.Data.DataSet>.</span></span>  
  
     <span data-ttu-id="c8573-117">En el ejemplo siguiente se muestra cómo establecer una relación principal-detalle entre las tablas Customers y Orders de <xref:System.Data.DataSet> un`ds`generado previamente ().</span><span class="sxs-lookup"><span data-stu-id="c8573-117">The following example shows how to set a master/detail relationship between the Customers and Orders tables in a previously generated <xref:System.Data.DataSet> (`ds`).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c8573-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8573-118">See also</span></span>

- [<span data-ttu-id="c8573-119">DataGrid (control)</span><span class="sxs-lookup"><span data-stu-id="c8573-119">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="c8573-120">Información general del control DataGrid</span><span class="sxs-lookup"><span data-stu-id="c8573-120">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="c8573-121">Procedimientos: Enlazar el control DataGrid de Windows Forms a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="c8573-121">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
