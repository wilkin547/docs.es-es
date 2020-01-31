---
title: Personalizar el control DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
ms.openlocfilehash: 348c78d091679418f2452326555d49229bd2a8ea
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744027"
---
# <a name="customizing-the-windows-forms-datagridview-control"></a><span data-ttu-id="e6da0-102">Personalizar el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e6da0-102">Customizing the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="e6da0-103">El control `DataGridView` proporciona varias propiedades que puede usar para ajustar la apariencia y el comportamiento básico (apariencia y funcionamiento) de sus celdas, filas y columnas.</span><span class="sxs-lookup"><span data-stu-id="e6da0-103">The `DataGridView` control provides several properties that you can use to adjust the appearance and basic behavior (look and feel) of its cells, rows, and columns.</span></span> <span data-ttu-id="e6da0-104">Sin embargo, si tiene necesidades especiales que van más allá de las capacidades de la clase <xref:System.Windows.Forms.DataGridViewCellStyle>, también puede implementar el dibujo del propietario para el control o ampliar sus capacidades creando celdas, columnas y filas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="e6da0-104">If you have special needs that go beyond the capabilities of the <xref:System.Windows.Forms.DataGridViewCellStyle> class, however, you can also implement owner drawing for the control or extend its capabilities by creating custom cells, columns, and rows.</span></span>  
  
 <span data-ttu-id="e6da0-105">Para pintar las celdas y las filas usted mismo, puede controlar diversos eventos de dibujo de `DataGridView`.</span><span class="sxs-lookup"><span data-stu-id="e6da0-105">To paint cells and rows yourself, you can handle various `DataGridView` painting events.</span></span> <span data-ttu-id="e6da0-106">Para modificar la funcionalidad existente o proporcionar una nueva funcionalidad, puede crear sus propios tipos derivados de los tipos de `DataGridViewCell`, `DataGridViewColumn`y `DataGridViewRow` existentes.</span><span class="sxs-lookup"><span data-stu-id="e6da0-106">To modify existing functionality or provide new functionality, you can create your own types derived from the existing `DataGridViewCell`, `DataGridViewColumn`, and `DataGridViewRow` types.</span></span> <span data-ttu-id="e6da0-107">También puede proporcionar nuevas capacidades de edición creando tipos derivados que muestren un control de su elección cuando una celda está en modo de edición.</span><span class="sxs-lookup"><span data-stu-id="e6da0-107">You can also provide new editing capabilities by creating derived types that display a control of your choosing when a cell is in edit mode.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e6da0-108">Esta sección</span><span class="sxs-lookup"><span data-stu-id="e6da0-108">In This Section</span></span>  
 [<span data-ttu-id="e6da0-109">Procedimiento para personalizar la apariencia de las celdas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e6da0-109">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-cells-in-the-datagrid.md)  
 <span data-ttu-id="e6da0-110">Describe cómo controlar el evento <xref:System.Windows.Forms.DataGridView.CellPainting> para pintar celdas manualmente.</span><span class="sxs-lookup"><span data-stu-id="e6da0-110">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellPainting> event in order to paint cells manually.</span></span>  
  
 [<span data-ttu-id="e6da0-111">Procedimiento para personalizar la apariencia de las filas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e6da0-111">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-rows-in-the-datagrid.md)  
 <span data-ttu-id="e6da0-112">Describe cómo controlar los eventos <xref:System.Windows.Forms.DataGridView.RowPrePaint> y <xref:System.Windows.Forms.DataGridView.RowPostPaint> para pintar filas con un fondo de degradado personalizado y contenido que abarca varias columnas.</span><span class="sxs-lookup"><span data-stu-id="e6da0-112">Describes how to handle the <xref:System.Windows.Forms.DataGridView.RowPrePaint> and <xref:System.Windows.Forms.DataGridView.RowPostPaint> events in order to paint rows with a custom, gradient background and content that spans multiple columns.</span></span>  
  
 [<span data-ttu-id="e6da0-113">Personalizar celdas y columnas en el control DataGridView de formularios Windows Forms ampliando su comportamiento y apariencia</span><span class="sxs-lookup"><span data-stu-id="e6da0-113">How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance</span></span>](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 <span data-ttu-id="e6da0-114">Describe cómo crear tipos personalizados derivados de `DataGridViewCell` y `DataGridViewColumn` para resaltar las celdas cuando el puntero del mouse se sitúa sobre ellas.</span><span class="sxs-lookup"><span data-stu-id="e6da0-114">Describes how to create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to highlight cells when the mouse pointer rests on them.</span></span>  
  
 [<span data-ttu-id="e6da0-115">Deshabilitar botones en una columna de botones del control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e6da0-115">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>](disable-buttons-in-a-button-column-in-the-datagrid.md)  
 <span data-ttu-id="e6da0-116">Describe cómo crear tipos personalizados derivados de <xref:System.Windows.Forms.DataGridViewButtonCell> y <xref:System.Windows.Forms.DataGridViewButtonColumn> para mostrar botones deshabilitados en una columna de botón.</span><span class="sxs-lookup"><span data-stu-id="e6da0-116">Describes how to create custom types derived from <xref:System.Windows.Forms.DataGridViewButtonCell> and <xref:System.Windows.Forms.DataGridViewButtonColumn> in order to display disabled buttons in a button column.</span></span>  
  
 [<span data-ttu-id="e6da0-117">Alojar controles en celdas DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e6da0-117">How to: Host Controls in Windows Forms DataGridView Cells</span></span>](how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 <span data-ttu-id="e6da0-118">Describe cómo implementar la interfaz de `IDataGridViewEditingControl` y crear tipos personalizados derivados de `DataGridViewCell` y `DataGridViewColumn` para mostrar un control de <xref:System.Windows.Forms.DateTimePicker> cuando una celda está en modo de edición.</span><span class="sxs-lookup"><span data-stu-id="e6da0-118">Describes how to implement the `IDataGridViewEditingControl` interface and create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to display a <xref:System.Windows.Forms.DateTimePicker> control when a cell is in edit mode.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e6da0-119">Referencia</span><span class="sxs-lookup"><span data-stu-id="e6da0-119">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="e6da0-120">Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="e6da0-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <span data-ttu-id="e6da0-121">Proporciona documentación de referencia para la clase <xref:System.Windows.Forms.DataGridViewCell>.</span><span class="sxs-lookup"><span data-stu-id="e6da0-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCell> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <span data-ttu-id="e6da0-122">Proporciona documentación de referencia para la clase <xref:System.Windows.Forms.DataGridViewRow>.</span><span class="sxs-lookup"><span data-stu-id="e6da0-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewRow> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <span data-ttu-id="e6da0-123">Proporciona documentación de referencia para la clase <xref:System.Windows.Forms.DataGridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="e6da0-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 <span data-ttu-id="e6da0-124">Proporciona documentación de referencia para la interfaz de <xref:System.Windows.Forms.IDataGridViewEditingControl>.</span><span class="sxs-lookup"><span data-stu-id="e6da0-124">Provides reference documentation for the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e6da0-125">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="e6da0-125">Related Sections</span></span>  
 [<span data-ttu-id="e6da0-126">Estilo y formato básicos del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e6da0-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e6da0-127">Proporciona temas que describen cómo modificar la apariencia básica del control y el formato de presentación de los datos de celda.</span><span class="sxs-lookup"><span data-stu-id="e6da0-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6da0-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6da0-128">See also</span></span>

- [<span data-ttu-id="e6da0-129">DataGridView (control)</span><span class="sxs-lookup"><span data-stu-id="e6da0-129">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="e6da0-130">Tipos de columnas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e6da0-130">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
