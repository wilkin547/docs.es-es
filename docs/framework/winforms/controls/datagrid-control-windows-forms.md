---
title: DataGrid (Control, formularios Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- datasets [Windows Forms], user interface
- DataGrid control [Windows Forms]
- datasets [Windows Forms], displaying in DataGrid control
- displaying data [Windows Forms], on forms
- data [Windows Forms], displaying on Windows Forms
ms.assetid: 1d9d5683-43d2-42dd-b6c3-e43f4cf0de99
ms.openlocfilehash: 5f8fcd21802c52d61d354c5ba85d665bd17237db
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078920"
---
# <a name="datagrid-control-windows-forms"></a><span data-ttu-id="1b8f6-102">DataGrid (Control, formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="1b8f6-102">DataGrid Control (Windows Forms)</span></span>
> [!NOTE]
>  <span data-ttu-id="1b8f6-103">El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control `DataGrid`; sin embargo, el control `DataGrid` se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="1b8f6-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the `DataGrid` control; however, the `DataGrid` control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="1b8f6-104">Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).</span><span class="sxs-lookup"><span data-stu-id="1b8f6-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="1b8f6-105">El control `DataGrid` de Windows Forms proporciona una interfaz de usuario para los conjuntos de datos [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], que muestra datos tabulares y habilita las actualizaciones para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="1b8f6-105">The Windows Forms `DataGrid` control provides a user interface to [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] datasets, displaying tabular data and enabling updates to the data source.</span></span>  
  
 <span data-ttu-id="1b8f6-106">Cuando el control `DataGrid` se establece en un origen de datos válido, se rellena automáticamente, y se crean columnas y filas basadas en la forma de los datos.</span><span class="sxs-lookup"><span data-stu-id="1b8f6-106">When the `DataGrid` control is set to a valid data source, the control is automatically populated, creating columns and rows based on the shape of the data.</span></span> <span data-ttu-id="1b8f6-107">El control `DataGrid` se puede usar para mostrar una única tabla o las relaciones jerárquicas entre un conjunto de tablas.</span><span class="sxs-lookup"><span data-stu-id="1b8f6-107">The `DataGrid` control can be used to display either a single table or the hierarchical relationships between a set of tables.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1b8f6-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1b8f6-108">In This Section</span></span>  
 [<span data-ttu-id="1b8f6-109">Información general del control DataGrid</span><span class="sxs-lookup"><span data-stu-id="1b8f6-109">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)  
 <span data-ttu-id="1b8f6-110">Describe las características básicas del control `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="1b8f6-110">Describes the basic features of the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="1b8f6-111">Cómo: Agregar tablas y columnas al Control DataGrid de formularios Windows mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="1b8f6-111">How to: Add Tables and Columns to the Windows Forms DataGrid Control Using the Designer</span></span>](add-tables-and-columns-to-wf-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="1b8f6-112">Describe cómo agregar tablas y columnas al control `DataGrid` mediante el diseñador.</span><span class="sxs-lookup"><span data-stu-id="1b8f6-112">Describes how to add tables and columns to the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="1b8f6-113">Cómo: Agregar tablas y columnas al Control DataGrid de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1b8f6-113">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="1b8f6-114">Describe cómo agregar tablas y columnas al control `DataGrid` mediante programación.</span><span class="sxs-lookup"><span data-stu-id="1b8f6-114">Describes how to add tables and columns to the `DataGrid` control programmatically.</span></span>  
  
 [<span data-ttu-id="1b8f6-115">Cómo: Enlazar el Control DataGrid de Windows Forms a un origen de datos mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="1b8f6-115">How to: Bind the Windows Forms DataGrid Control to a Data Source Using the Designer</span></span>](bind-wf-datagrid-control-to-a-data-source-using-the-designer.md)  
 <span data-ttu-id="1b8f6-116">Describe cómo enlazar un conjunto de datos [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] al control `DataGrid` mediante el diseñador.</span><span class="sxs-lookup"><span data-stu-id="1b8f6-116">Describes how to bind an [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] dataset to the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="1b8f6-117">Cómo: Enlazar el Control DataGrid de Windows Forms a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="1b8f6-117">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)  
 <span data-ttu-id="1b8f6-118">Describe cómo enlazar un conjunto de datos [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] al control `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="1b8f6-118">Describes how to bind an [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] dataset to the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="1b8f6-119">Cómo: Cambiar los datos mostrados en tiempo de ejecución en el Control DataGrid de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1b8f6-119">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>](change-displayed-data-at-run-time-wf-datagrid-control.md)  
 <span data-ttu-id="1b8f6-120">Describe cómo cambiar datos mediante programación en el control `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="1b8f6-120">Describes how to change data programmatically in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="1b8f6-121">Cómo: Crear listas principal-detalle con el Control DataGrid de Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="1b8f6-121">How to: Create Master-Details Lists with the Windows Forms DataGrid Control Using the Designer</span></span>](create-master-details-lists-with-wf-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="1b8f6-122">Describe cómo mostrar dos tablas, enlazadas entre sí mediante una relación primario-secundario, en dos controles `DataGrid` independientes mediante el diseñador.</span><span class="sxs-lookup"><span data-stu-id="1b8f6-122">Describes how to display two tables, tied together with a parent/child relationship, in two separate `DataGrid` controls using the designer.</span></span>  
  
 <span data-ttu-id="1b8f6-123">Procedimiento Crear listas principal-detalle con el Control DataGrid de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1b8f6-123">How to: Create Master-Details Lists with the Windows Forms DataGrid Control</span></span>  
 <span data-ttu-id="1b8f6-124">Describe cómo mostrar dos tablas, enlazadas entre sí mediante una relación primario-secundario, en dos controles `DataGrid` independientes mediante el diseñador.</span><span class="sxs-lookup"><span data-stu-id="1b8f6-124">Describes how to display two tables, tied together with a parent/child relationship, in two separate `DataGrid` controls.</span></span>  
  
 [<span data-ttu-id="1b8f6-125">Cómo: Eliminar u ocultar columnas en el Control DataGrid de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1b8f6-125">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="1b8f6-126">Describe cómo quitar columnas del control `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="1b8f6-126">Describes how to remove columns in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="1b8f6-127">Cómo: Dar formato el Control DataGrid de Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="1b8f6-127">How to: Format the Windows Forms DataGrid Control Using the Designer</span></span>](how-to-format-the-windows-forms-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="1b8f6-128">Describe cómo cambiar las propiedades relacionadas con la apariencia del control `DataGrid` mediante el diseñador.</span><span class="sxs-lookup"><span data-stu-id="1b8f6-128">Describes how to change the appearance-related properties of the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="1b8f6-129">Cómo: Formato al Control DataGrid de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="1b8f6-129">How to: Format the Windows Forms DataGrid Control</span></span>](how-to-format-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="1b8f6-130">Describe cómo cambiar las propiedades relacionadas con la apariencia del control `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="1b8f6-130">Describes how to change the appearance-related properties of the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="1b8f6-131">Métodos abreviados de teclado para el control DataGrid de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1b8f6-131">Keyboard Shortcuts for the Windows Forms DataGrid Control</span></span>](keyboard-shortcuts-for-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="1b8f6-132">Muestra combinaciones de teclas para navegar por el control `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="1b8f6-132">Lists shortcuts for navigating through the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="1b8f6-133">Cómo: Responder a clics en el Control DataGrid de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1b8f6-133">How to: Respond to Clicks in the Windows Forms DataGrid Control</span></span>](how-to-respond-to-clicks-in-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="1b8f6-134">Describe cómo determinar la celda en la que hizo clic un usuario en el control `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="1b8f6-134">Describes how to determine which cell a user has clicked in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="1b8f6-135">Cómo: Validar la entrada con el Control DataGrid de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1b8f6-135">How to: Validate Input with the Windows Forms DataGrid Control</span></span>](how-to-validate-input-with-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="1b8f6-136">Describe cómo validar la entrada en el conjunto de datos enlazado al control `DataGrid`.</span><span class="sxs-lookup"><span data-stu-id="1b8f6-136">Describes how to validate input in the dataset bound to the `DataGrid` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1b8f6-137">Referencia</span><span class="sxs-lookup"><span data-stu-id="1b8f6-137">Reference</span></span>  
 <xref:System.Windows.Forms.DataGrid>  
 <span data-ttu-id="1b8f6-138">Proporciona información general sobre la <xref:System.Windows.Forms.DataGrid> clase.</span><span class="sxs-lookup"><span data-stu-id="1b8f6-138">Provides an overview of the <xref:System.Windows.Forms.DataGrid> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGrid.DataSource%2A>  
 <span data-ttu-id="1b8f6-139">Proporciona información detallada sobre el uso de esta propiedad para enlazar el <xref:System.Windows.Forms.DataGrid> control a los datos.</span><span class="sxs-lookup"><span data-stu-id="1b8f6-139">Provides details about using this property to bind the <xref:System.Windows.Forms.DataGrid> control to data.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1b8f6-140">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="1b8f6-140">Related Sections</span></span>  
 [<span data-ttu-id="1b8f6-141">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1b8f6-141">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)  
 <span data-ttu-id="1b8f6-142">Proporciona vínculos a temas sobre el enlace de datos en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="1b8f6-142">Provides links to topics on data binding in Windows Forms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b8f6-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b8f6-143">See also</span></span>

- [<span data-ttu-id="1b8f6-144">DataGridView (control)</span><span class="sxs-lookup"><span data-stu-id="1b8f6-144">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="1b8f6-145">Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1b8f6-145">Differences Between the Windows Forms DataGridView and DataGrid Controls</span></span>](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)
