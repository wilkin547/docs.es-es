---
title: Control DataGrid
ms.date: 03/30/2017
helpviewer_keywords:
- datasets [Windows Forms], user interface
- DataGrid control [Windows Forms]
- datasets [Windows Forms], displaying in DataGrid control
- displaying data [Windows Forms], on forms
- data [Windows Forms], displaying on Windows Forms
ms.assetid: 1d9d5683-43d2-42dd-b6c3-e43f4cf0de99
ms.openlocfilehash: efcc8770232f657c13135cefb4027f814d4d7d19
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742519"
---
# <a name="datagrid-control-windows-forms"></a><span data-ttu-id="f052a-102">DataGrid (Control, formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="f052a-102">DataGrid Control (Windows Forms)</span></span>
> [!NOTE]
> <span data-ttu-id="f052a-103">El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control `DataGrid`; sin embargo, el control `DataGrid` se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="f052a-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the `DataGrid` control; however, the `DataGrid` control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="f052a-104">Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).</span><span class="sxs-lookup"><span data-stu-id="f052a-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="f052a-105">El control Windows Forms `DataGrid` proporciona una interfaz de usuario para ADO.NET conjuntos de datos, que muestra los datos tabulares y habilita las actualizaciones en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="f052a-105">The Windows Forms `DataGrid` control provides a user interface to ADO.NET datasets, displaying tabular data and enabling updates to the data source.</span></span>  
  
 <span data-ttu-id="f052a-106">Cuando el control `DataGrid` se establece en un origen de datos válido, se rellena automáticamente, y se crean columnas y filas basadas en la forma de los datos.</span><span class="sxs-lookup"><span data-stu-id="f052a-106">When the `DataGrid` control is set to a valid data source, the control is automatically populated, creating columns and rows based on the shape of the data.</span></span> <span data-ttu-id="f052a-107">El control `DataGrid` se puede usar para mostrar una única tabla o las relaciones jerárquicas entre un conjunto de tablas.</span><span class="sxs-lookup"><span data-stu-id="f052a-107">The `DataGrid` control can be used to display either a single table or the hierarchical relationships between a set of tables.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f052a-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f052a-108">In This Section</span></span>  
 [<span data-ttu-id="f052a-109">Información general del control DataGrid</span><span class="sxs-lookup"><span data-stu-id="f052a-109">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)  
 <span data-ttu-id="f052a-110">Describe las características básicas del control `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="f052a-110">Describes the basic features of the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="f052a-111">Cómo: Agregar tablas y columnas al control DataGrid de formularios Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="f052a-111">How to: Add Tables and Columns to the Windows Forms DataGrid Control Using the Designer</span></span>](add-tables-and-columns-to-wf-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="f052a-112">Describe cómo agregar tablas y columnas al control `DataGrid` mediante el diseñador.</span><span class="sxs-lookup"><span data-stu-id="f052a-112">Describes how to add tables and columns to the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="f052a-113">Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f052a-113">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="f052a-114">Describe cómo agregar tablas y columnas al control `DataGrid` mediante programación.</span><span class="sxs-lookup"><span data-stu-id="f052a-114">Describes how to add tables and columns to the `DataGrid` control programmatically.</span></span>  
  
 [<span data-ttu-id="f052a-115">Cómo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="f052a-115">How to: Bind the Windows Forms DataGrid Control to a Data Source Using the Designer</span></span>](bind-wf-datagrid-control-to-a-data-source-using-the-designer.md)  
 <span data-ttu-id="f052a-116">Describe cómo enlazar un conjunto de ADO.NET al control de `DataGrid` mediante el diseñador.</span><span class="sxs-lookup"><span data-stu-id="f052a-116">Describes how to bind an ADO.NET dataset to the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="f052a-117">Cómo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="f052a-117">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)  
 <span data-ttu-id="f052a-118">Describe cómo enlazar un conjunto de ADO.NET al control de `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="f052a-118">Describes how to bind an ADO.NET dataset to the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="f052a-119">Cómo: Cambiar los datos mostrados en tiempo de ejecución en el control DataGrid de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f052a-119">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>](change-displayed-data-at-run-time-wf-datagrid-control.md)  
 <span data-ttu-id="f052a-120">Describe cómo cambiar datos mediante programación en el control `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="f052a-120">Describes how to change data programmatically in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="f052a-121">Cómo: Crear listas Principal-Detalle con el control DataGrid de Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="f052a-121">How to: Create Master-Details Lists with the Windows Forms DataGrid Control Using the Designer</span></span>](create-master-details-lists-with-wf-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="f052a-122">Describe cómo mostrar dos tablas, enlazadas entre sí mediante una relación primario-secundario, en dos controles `DataGrid` independientes mediante el diseñador.</span><span class="sxs-lookup"><span data-stu-id="f052a-122">Describes how to display two tables, tied together with a parent/child relationship, in two separate `DataGrid` controls using the designer.</span></span>  
  
 <span data-ttu-id="f052a-123">Cómo: Crear listas principal-detalle con el control DataGrid de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f052a-123">How to: Create Master-Details Lists with the Windows Forms DataGrid Control</span></span>  
 <span data-ttu-id="f052a-124">Describe cómo mostrar dos tablas, enlazadas entre sí mediante una relación primario-secundario, en dos controles `DataGrid` independientes mediante el diseñador.</span><span class="sxs-lookup"><span data-stu-id="f052a-124">Describes how to display two tables, tied together with a parent/child relationship, in two separate `DataGrid` controls.</span></span>  
  
 [<span data-ttu-id="f052a-125">Cómo: Eliminar u ocultar columnas del control DataGrid de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f052a-125">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="f052a-126">Describe cómo quitar columnas del control `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="f052a-126">Describes how to remove columns in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="f052a-127">Cómo: Dar formato al control DataGrid de formularios Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="f052a-127">How to: Format the Windows Forms DataGrid Control Using the Designer</span></span>](how-to-format-the-windows-forms-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="f052a-128">Describe cómo cambiar las propiedades relacionadas con la apariencia del control `DataGrid` mediante el diseñador.</span><span class="sxs-lookup"><span data-stu-id="f052a-128">Describes how to change the appearance-related properties of the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="f052a-129">Procedimiento para dar formato al control DataGrid de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f052a-129">How to: Format the Windows Forms DataGrid Control</span></span>](how-to-format-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="f052a-130">Describe cómo cambiar las propiedades relacionadas con la apariencia del control `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="f052a-130">Describes how to change the appearance-related properties of the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="f052a-131">Métodos abreviados de teclado para el control DataGrid de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f052a-131">Keyboard Shortcuts for the Windows Forms DataGrid Control</span></span>](keyboard-shortcuts-for-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="f052a-132">Muestra combinaciones de teclas para navegar por el control `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="f052a-132">Lists shortcuts for navigating through the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="f052a-133">Cómo: Responder a clics en el control DataGrid de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f052a-133">How to: Respond to Clicks in the Windows Forms DataGrid Control</span></span>](how-to-respond-to-clicks-in-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="f052a-134">Describe cómo determinar la celda en la que hizo clic un usuario en el control `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="f052a-134">Describes how to determine which cell a user has clicked in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="f052a-135">Cómo: Validar los datos introducidos con el control DataGrid de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f052a-135">How to: Validate Input with the Windows Forms DataGrid Control</span></span>](how-to-validate-input-with-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="f052a-136">Describe cómo validar la entrada en el conjunto de datos enlazado al control `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="f052a-136">Describes how to validate input in the dataset bound to the `DataGrid` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f052a-137">Referencia</span><span class="sxs-lookup"><span data-stu-id="f052a-137">Reference</span></span>  
 <xref:System.Windows.Forms.DataGrid>  
 <span data-ttu-id="f052a-138">Proporciona información general sobre la clase <xref:System.Windows.Forms.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="f052a-138">Provides an overview of the <xref:System.Windows.Forms.DataGrid> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGrid.DataSource%2A>  
 <span data-ttu-id="f052a-139">Proporciona detalles sobre el uso de esta propiedad para enlazar el control <xref:System.Windows.Forms.DataGrid> a los datos.</span><span class="sxs-lookup"><span data-stu-id="f052a-139">Provides details about using this property to bind the <xref:System.Windows.Forms.DataGrid> control to data.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f052a-140">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="f052a-140">Related Sections</span></span>  
 [<span data-ttu-id="f052a-141">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f052a-141">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)  
 <span data-ttu-id="f052a-142">Proporciona vínculos a temas sobre el enlace de datos en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f052a-142">Provides links to topics on data binding in Windows Forms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f052a-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f052a-143">See also</span></span>

- [<span data-ttu-id="f052a-144">DataGridView (control)</span><span class="sxs-lookup"><span data-stu-id="f052a-144">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="f052a-145">Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f052a-145">Differences Between the Windows Forms DataGridView and DataGrid Controls</span></span>](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)
