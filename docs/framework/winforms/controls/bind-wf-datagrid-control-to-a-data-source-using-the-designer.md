---
title: "Cómo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos mediante el Diseñador"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- Windows Forms controls, data binding
- bound controls [Windows Forms]
ms.assetid: 4e96e3d0-b1cc-4de1-8774-bc9970ec4554
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3913ffe046bb55e31d8be223061af61371a47418
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source-using-the-designer"></a><span data-ttu-id="da653-102">Cómo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="da653-102">How to: Bind the Windows Forms DataGrid Control to a Data Source Using the Designer</span></span>
> [!NOTE]
>  <span data-ttu-id="da653-103">El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="da653-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="da653-104">Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).</span><span class="sxs-lookup"><span data-stu-id="da653-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="da653-105">Los formularios Windows Forms <xref:System.Windows.Forms.DataGrid> control está diseñado específicamente para mostrar información de un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="da653-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="da653-106">Enlazar el control en tiempo de diseño estableciendo la <xref:System.Windows.Forms.DataGrid.DataSource%2A> y <xref:System.Windows.Forms.DataGrid.DataMember%2A> propiedades, o en tiempo de ejecución mediante una llamada a la <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método.</span><span class="sxs-lookup"><span data-stu-id="da653-106">You bind the control at design time by setting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties, or at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="da653-107">Aunque se pueden mostrar datos desde una variedad de orígenes de datos, los orígenes más habituales son vistas de datos y conjuntos de datos.</span><span class="sxs-lookup"><span data-stu-id="da653-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>  
  
 <span data-ttu-id="da653-108">Si el origen de datos está disponible en tiempo de diseño, por ejemplo, si el formulario contiene una instancia de un conjunto de datos o una vista de datos, puede enlazar la cuadrícula al origen de datos en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="da653-108">If the data source is available at design time—for example, if the form contains an instance of a dataset or a data view—you can bind the grid to the data source at design time.</span></span> <span data-ttu-id="da653-109">A continuación, puede ver el aspecto de los datos en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="da653-109">You can then preview what the data will look like in the grid.</span></span>  
  
 <span data-ttu-id="da653-110">También puede enlazar mediante programación, la cuadrícula en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="da653-110">You can also bind the grid programmatically, at run time.</span></span> <span data-ttu-id="da653-111">Esto es útil cuando desea establecer un origen de datos basado en la información que se obtienen en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="da653-111">This is useful when you want to set a data source based on information you get at run time.</span></span> <span data-ttu-id="da653-112">Por ejemplo, la aplicación podría permiten al usuario especificar el nombre de tabla que desea ver.</span><span class="sxs-lookup"><span data-stu-id="da653-112">For example, the application might let the user specify the name of a table to view.</span></span> <span data-ttu-id="da653-113">También es necesario en situaciones donde el origen de datos no existe en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="da653-113">It is also necessary in situations where the data source does not exist at design time.</span></span> <span data-ttu-id="da653-114">Esto incluye orígenes de datos como matrices, colecciones, conjuntos de datos sin tipo y lectores de datos.</span><span class="sxs-lookup"><span data-stu-id="da653-114">This includes data sources such as arrays, collections, untyped datasets, and data readers.</span></span>  
  
 <span data-ttu-id="da653-115">El procedimiento siguiente requiere un **aplicación de Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.DataGrid> control.</span><span class="sxs-lookup"><span data-stu-id="da653-115">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="da653-116">Para obtener información acerca de cómo configurar un proyecto de este tipo, consulte [Cómo: crear un proyecto de aplicación de Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="da653-116">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span> <span data-ttu-id="da653-117">En [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], <xref:System.Windows.Forms.DataGrid> control no está en el **cuadro de herramientas** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="da653-117">In [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], the <xref:System.Windows.Forms.DataGrid> control is not in the **Toolbox** by default.</span></span> <span data-ttu-id="da653-118">Para obtener información sobre cómo agregarlo, vea [Cómo: agregar elementos al cuadro de herramientas](http://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0).</span><span class="sxs-lookup"><span data-stu-id="da653-118">For information about adding it, see [How to: Add Items to the Toolbox](http://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0).</span></span> <span data-ttu-id="da653-119">Además de [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], puede usar el **orígenes de datos** ventana para el enlace de datos en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="da653-119">Additionally in [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], you can use the **Data Sources** window for design-time data binding.</span></span> <span data-ttu-id="da653-120">Para obtener más información, consulte [enlazar controles a datos en Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="da653-120">For more information see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="da653-121">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="da653-121">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="da653-122">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="da653-122">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="da653-123">Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="da653-123">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-to-a-single-table-in-the-designer"></a><span data-ttu-id="da653-124">Para enlazar el control DataGrid a una sola tabla en el diseñador</span><span class="sxs-lookup"><span data-stu-id="da653-124">To data-bind the DataGrid control to a single table in the designer</span></span>  
  
1.  <span data-ttu-id="da653-125">Establecer el control <xref:System.Windows.Forms.DataGrid.DataSource%2A> propiedad para el objeto que contiene los elementos de datos que desea enlazar.</span><span class="sxs-lookup"><span data-stu-id="da653-125">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>  
  
2.  <span data-ttu-id="da653-126">Si el origen de datos es un conjunto de datos, establezca la <xref:System.Windows.Forms.DataGrid.DataMember%2A> propiedad en el nombre de la tabla que se va a enlazar a.</span><span class="sxs-lookup"><span data-stu-id="da653-126">If the data source is a dataset, set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the table to bind to.</span></span>  
  
3.  <span data-ttu-id="da653-127">Si el origen de datos es un conjunto de datos o una vista de datos basada en una tabla de conjunto de datos, agregue código al formulario para rellenar el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="da653-127">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>  
  
     <span data-ttu-id="da653-128">El código exacto que utilice depende de que el conjunto de datos está obteniendo datos.</span><span class="sxs-lookup"><span data-stu-id="da653-128">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="da653-129">Si se está llenando el conjunto de datos directamente desde una base de datos, normalmente se invoca el `Fill` método de un adaptador de datos, como en el ejemplo de código siguiente, que rellena un conjunto de datos denominado `DsCategories1`:</span><span class="sxs-lookup"><span data-stu-id="da653-129">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following code example, which populates a dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
4.  <span data-ttu-id="da653-130">(Opcional) Agregar los estilos de tabla adecuado y estilos de columna a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="da653-130">(Optional) Add the appropriate table styles and column styles to the grid.</span></span>  
  
     <span data-ttu-id="da653-131">Si no hay ningún estilo de tabla, verá la tabla, pero con un formato mínimo y con todas las columnas visibles.</span><span class="sxs-lookup"><span data-stu-id="da653-131">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-to-multiple-tables-in-a-dataset-in-the-designer"></a><span data-ttu-id="da653-132">Para enlazar el control DataGrid a varias tablas en un conjunto de datos en el diseñador</span><span class="sxs-lookup"><span data-stu-id="da653-132">To data-bind the DataGrid control to multiple tables in a dataset in the designer</span></span>  
  
1.  <span data-ttu-id="da653-133">Establecer el control <xref:System.Windows.Forms.DataGrid.DataSource%2A> propiedad para el objeto que contiene los elementos de datos que desea enlazar.</span><span class="sxs-lookup"><span data-stu-id="da653-133">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>  
  
2.  <span data-ttu-id="da653-134">Si el conjunto de datos contiene tablas relacionadas (es decir, si contiene un objeto relation), establezca el <xref:System.Windows.Forms.DataGrid.DataMember%2A> propiedad en el nombre de la tabla primaria.</span><span class="sxs-lookup"><span data-stu-id="da653-134">If the dataset contains related tables (that is, if it contains a relation object), set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the parent table.</span></span>  
  
3.  <span data-ttu-id="da653-135">Escribir código para llenar el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="da653-135">Write code to fill the dataset.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da653-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="da653-136">See Also</span></span>  
 [<span data-ttu-id="da653-137">Información general del control DataGrid</span><span class="sxs-lookup"><span data-stu-id="da653-137">DataGrid Control Overview</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [<span data-ttu-id="da653-138">Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da653-138">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 [<span data-ttu-id="da653-139">DataGrid (control)</span><span class="sxs-lookup"><span data-stu-id="da653-139">DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [<span data-ttu-id="da653-140">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da653-140">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="da653-141">Obtener acceso a los datos en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="da653-141">Accessing data in Visual Studio</span></span>](/visualstudio/data-tools/accessing-data-in-visual-studio)
