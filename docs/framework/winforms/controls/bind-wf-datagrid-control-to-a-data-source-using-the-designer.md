---
title: Enlazar el control DataGrid a un origen de datos mediante el diseñador
ms.date: 03/30/2017
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
ms.openlocfilehash: cc0a74eca40e34f06b065980d25d922b919b0c3c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744090"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source-using-the-designer"></a><span data-ttu-id="a7521-102">Cómo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="a7521-102">How to: Bind the Windows Forms DataGrid Control to a Data Source Using the Designer</span></span>

> [!NOTE]
> <span data-ttu-id="a7521-103">El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="a7521-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="a7521-104">Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).</span><span class="sxs-lookup"><span data-stu-id="a7521-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>

 <span data-ttu-id="a7521-105">El control <xref:System.Windows.Forms.DataGrid> de Windows Forms está diseñado específicamente para mostrar información de un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="a7521-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="a7521-106">Para enlazar el control en tiempo de diseño, establezca las propiedades <xref:System.Windows.Forms.DataGrid.DataSource%2A> y <xref:System.Windows.Forms.DataGrid.DataMember%2A>, o en tiempo de ejecución mediante una llamada al método <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>.</span><span class="sxs-lookup"><span data-stu-id="a7521-106">You bind the control at design time by setting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties, or at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="a7521-107">Aunque puede mostrar los datos de diversos orígenes de datos, los orígenes más habituales son los conjuntos de datos y las vistas de datos.</span><span class="sxs-lookup"><span data-stu-id="a7521-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>

 <span data-ttu-id="a7521-108">Si el origen de datos está disponible en tiempo de diseño (por ejemplo, si el formulario contiene una instancia de un conjunto de datos o una vista de datos), puede enlazar la cuadrícula al origen de datos en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="a7521-108">If the data source is available at design time—for example, if the form contains an instance of a dataset or a data view—you can bind the grid to the data source at design time.</span></span> <span data-ttu-id="a7521-109">Después, puede obtener una vista previa de la apariencia de los datos en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="a7521-109">You can then preview what the data will look like in the grid.</span></span>

 <span data-ttu-id="a7521-110">También puede enlazar la cuadrícula mediante programación, en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a7521-110">You can also bind the grid programmatically, at run time.</span></span> <span data-ttu-id="a7521-111">Esto resulta útil cuando se desea establecer un origen de datos basado en la información que se obtiene en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a7521-111">This is useful when you want to set a data source based on information you get at run time.</span></span> <span data-ttu-id="a7521-112">Por ejemplo, la aplicación puede permitir que el usuario especifique el nombre de una tabla para ver.</span><span class="sxs-lookup"><span data-stu-id="a7521-112">For example, the application might let the user specify the name of a table to view.</span></span> <span data-ttu-id="a7521-113">También es necesario en situaciones en las que el origen de datos no existe en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="a7521-113">It is also necessary in situations where the data source does not exist at design time.</span></span> <span data-ttu-id="a7521-114">Esto incluye orígenes de datos como matrices, colecciones, conjuntos de datos sin tipo y lectores de datos.</span><span class="sxs-lookup"><span data-stu-id="a7521-114">This includes data sources such as arrays, collections, untyped datasets, and data readers.</span></span>

 <span data-ttu-id="a7521-115">El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que contenga un control <xref:System.Windows.Forms.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="a7521-115">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="a7521-116">Para obtener información sobre cómo configurar este tipo de proyecto, vea [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="a7521-116">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span> <span data-ttu-id="a7521-117">En Visual Studio 2005, el control <xref:System.Windows.Forms.DataGrid> no está en el **cuadro de herramientas** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a7521-117">In Visual Studio 2005, the <xref:System.Windows.Forms.DataGrid> control is not in the **Toolbox** by default.</span></span> <span data-ttu-id="a7521-118">Para obtener información sobre cómo agregarlo, vea [Cómo: agregar elementos al cuadro de herramientas](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="a7521-118">For information about adding it, see [How to: Add Items to the Toolbox](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).</span></span> <span data-ttu-id="a7521-119">Además, en Visual Studio 2005, puede usar la ventana **orígenes de datos** para el enlace de datos en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="a7521-119">Additionally in Visual Studio 2005, you can use the **Data Sources** window for design-time data binding.</span></span> <span data-ttu-id="a7521-120">Para obtener más información, vea [enlazar controles a datos en Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="a7521-120">For more information see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span></span>

## <a name="to-data-bind-the-datagrid-control-to-a-single-table-in-the-designer"></a><span data-ttu-id="a7521-121">Para enlazar datos al control DataGrid a una sola tabla en el diseñador</span><span class="sxs-lookup"><span data-stu-id="a7521-121">To data-bind the DataGrid control to a single table in the designer</span></span>

1. <span data-ttu-id="a7521-122">Establezca la propiedad <xref:System.Windows.Forms.DataGrid.DataSource%2A> del control en el objeto que contiene los elementos de datos a los que desea enlazar.</span><span class="sxs-lookup"><span data-stu-id="a7521-122">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>

2. <span data-ttu-id="a7521-123">Si el origen de datos es un conjunto de datos, establezca la propiedad <xref:System.Windows.Forms.DataGrid.DataMember%2A> en el nombre de la tabla a la que se va a enlazar.</span><span class="sxs-lookup"><span data-stu-id="a7521-123">If the data source is a dataset, set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the table to bind to.</span></span>

3. <span data-ttu-id="a7521-124">Si el origen de datos es un conjunto de datos o una vista de datos basada en una tabla de conjunto de datos, agregue código al formulario para rellenar el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="a7521-124">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>

     <span data-ttu-id="a7521-125">El código exacto que se utiliza depende de la ubicación del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="a7521-125">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="a7521-126">Si el conjunto de datos se rellena directamente desde una base de datos, normalmente se llama al método `Fill` de un adaptador de datos, como en el ejemplo de código siguiente, que rellena un conjunto de datos denominado `DsCategories1`:</span><span class="sxs-lookup"><span data-stu-id="a7521-126">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following code example, which populates a dataset called `DsCategories1`:</span></span>

    ```vb
    sqlDataAdapter1.Fill(DsCategories1)
    ```

    ```csharp
    sqlDataAdapter1.Fill(DsCategories1);
    ```

    ```cpp
    sqlDataAdapter1->Fill(dsCategories1);
    ```

4. <span data-ttu-id="a7521-127">Opta Agregue los estilos de tabla y de columna correspondientes a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="a7521-127">(Optional) Add the appropriate table styles and column styles to the grid.</span></span>

     <span data-ttu-id="a7521-128">Si no hay ningún estilo de tabla, verá la tabla, pero con el formato mínimo y con todas las columnas visibles.</span><span class="sxs-lookup"><span data-stu-id="a7521-128">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>

## <a name="to-data-bind-the-datagrid-control-to-multiple-tables-in-a-dataset-in-the-designer"></a><span data-ttu-id="a7521-129">Para enlazar datos al control DataGrid en varias tablas de un conjunto de datos en el diseñador</span><span class="sxs-lookup"><span data-stu-id="a7521-129">To data-bind the DataGrid control to multiple tables in a dataset in the designer</span></span>

1. <span data-ttu-id="a7521-130">Establezca la propiedad <xref:System.Windows.Forms.DataGrid.DataSource%2A> del control en el objeto que contiene los elementos de datos a los que desea enlazar.</span><span class="sxs-lookup"><span data-stu-id="a7521-130">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>

2. <span data-ttu-id="a7521-131">Si el conjunto de elementos contiene tablas relacionadas (es decir, si contiene un objeto de relación), establezca la propiedad <xref:System.Windows.Forms.DataGrid.DataMember%2A> en el nombre de la tabla primaria.</span><span class="sxs-lookup"><span data-stu-id="a7521-131">If the dataset contains related tables (that is, if it contains a relation object), set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the parent table.</span></span>

3. <span data-ttu-id="a7521-132">Escriba código para rellenar el conjunto de DataSet.</span><span class="sxs-lookup"><span data-stu-id="a7521-132">Write code to fill the dataset.</span></span>

## <a name="see-also"></a><span data-ttu-id="a7521-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a7521-133">See also</span></span>

- [<span data-ttu-id="a7521-134">Información general del control DataGrid</span><span class="sxs-lookup"><span data-stu-id="a7521-134">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="a7521-135">Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a7521-135">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="a7521-136">DataGrid (control)</span><span class="sxs-lookup"><span data-stu-id="a7521-136">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="a7521-137">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a7521-137">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="a7521-138">Obtener acceso a los datos en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a7521-138">Accessing data in Visual Studio</span></span>](/visualstudio/data-tools/accessing-data-in-visual-studio)
