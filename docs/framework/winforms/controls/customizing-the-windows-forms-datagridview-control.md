---
title: Personalizar el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
ms.openlocfilehash: 901b221f74fa76221ed3f19e9eb4c5f17c6534fa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559559"
---
# <a name="customizing-the-windows-forms-datagridview-control"></a><span data-ttu-id="af1fd-102">Personalizar el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af1fd-102">Customizing the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="af1fd-103">El `DataGridView` control proporciona varias propiedades que puede usar para ajustar la apariencia y comportamiento básico (apariencia) de sus celdas, filas y columnas.</span><span class="sxs-lookup"><span data-stu-id="af1fd-103">The `DataGridView` control provides several properties that you can use to adjust the appearance and basic behavior (look and feel) of its cells, rows, and columns.</span></span> <span data-ttu-id="af1fd-104">Si tiene necesidades especiales que van más allá de las capacidades de la <xref:System.Windows.Forms.DataGridViewCellStyle> class, sin embargo, también puede implementar para el control de dibujo del propietario o ampliar sus capacidades mediante la creación personalizadas celdas, columnas y filas.</span><span class="sxs-lookup"><span data-stu-id="af1fd-104">If you have special needs that go beyond the capabilities of the <xref:System.Windows.Forms.DataGridViewCellStyle> class, however, you can also implement owner drawing for the control or extend its capabilities by creating custom cells, columns, and rows.</span></span>  
  
 <span data-ttu-id="af1fd-105">Para pintar las celdas y filas usted mismo, puede controlar varios `DataGridView` eventos de dibujo.</span><span class="sxs-lookup"><span data-stu-id="af1fd-105">To paint cells and rows yourself, you can handle various `DataGridView` painting events.</span></span> <span data-ttu-id="af1fd-106">Para modificar la funcionalidad existente o proporcionar nueva funcionalidad, puede crear sus propios tipos derivados de las existentes `DataGridViewCell`, `DataGridViewColumn`, y `DataGridViewRow` tipos.</span><span class="sxs-lookup"><span data-stu-id="af1fd-106">To modify existing functionality or provide new functionality, you can create your own types derived from the existing `DataGridViewCell`, `DataGridViewColumn`, and `DataGridViewRow` types.</span></span> <span data-ttu-id="af1fd-107">También puede proporcionar nuevas capacidades de edición mediante la creación de tipos derivados que muestran un control de su elección cuando una celda está en modo de edición.</span><span class="sxs-lookup"><span data-stu-id="af1fd-107">You can also provide new editing capabilities by creating derived types that display a control of your choosing when a cell is in edit mode.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="af1fd-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="af1fd-108">In This Section</span></span>  
 [<span data-ttu-id="af1fd-109">Cómo: Personalizar la apariencia de celdas en el Control DataGridView de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="af1fd-109">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
 <span data-ttu-id="af1fd-110">Describe cómo controlar la <xref:System.Windows.Forms.DataGridView.CellPainting> eventos con el fin de dibujar celdas manualmente.</span><span class="sxs-lookup"><span data-stu-id="af1fd-110">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellPainting> event in order to paint cells manually.</span></span>  
  
 [<span data-ttu-id="af1fd-111">Cómo: Personalizar la apariencia de las filas en el Control DataGridView de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="af1fd-111">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
 <span data-ttu-id="af1fd-112">Describe cómo controlar la <xref:System.Windows.Forms.DataGridView.RowPrePaint> y <xref:System.Windows.Forms.DataGridView.RowPostPaint> eventos con el fin de dibujar filas con un fondo personalizado, degradado y contenido que abarca varias columnas.</span><span class="sxs-lookup"><span data-stu-id="af1fd-112">Describes how to handle the <xref:System.Windows.Forms.DataGridView.RowPrePaint> and <xref:System.Windows.Forms.DataGridView.RowPostPaint> events in order to paint rows with a custom, gradient background and content that spans multiple columns.</span></span>  
  
 [<span data-ttu-id="af1fd-113">Cómo: Personalizar celdas y columnas en el Control DataGridView de Windows Forms ampliando su comportamiento y apariencia</span><span class="sxs-lookup"><span data-stu-id="af1fd-113">How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance</span></span>](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 <span data-ttu-id="af1fd-114">Describe cómo crear tipos personalizados derivados de `DataGridViewCell` y `DataGridViewColumn` con el fin de resaltar celdas cuando el puntero del mouse se sitúa sobre ellos.</span><span class="sxs-lookup"><span data-stu-id="af1fd-114">Describes how to create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to highlight cells when the mouse pointer rests on them.</span></span>  
  
 [<span data-ttu-id="af1fd-115">Cómo: Deshabilitar botones en una columna de botones en el Control DataGridView de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="af1fd-115">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/disable-buttons-in-a-button-column-in-the-datagrid.md)  
 <span data-ttu-id="af1fd-116">Describe cómo crear tipos personalizados derivados de <xref:System.Windows.Forms.DataGridViewButtonCell> y <xref:System.Windows.Forms.DataGridViewButtonColumn> con el fin de mostrar los botones deshabilitados en una columna de botones.</span><span class="sxs-lookup"><span data-stu-id="af1fd-116">Describes how to create custom types derived from <xref:System.Windows.Forms.DataGridViewButtonCell> and <xref:System.Windows.Forms.DataGridViewButtonColumn> in order to display disabled buttons in a button column.</span></span>  
  
 [<span data-ttu-id="af1fd-117">Cómo: Hospedar controles en celdas DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af1fd-117">How to: Host Controls in Windows Forms DataGridView Cells</span></span>](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 <span data-ttu-id="af1fd-118">Describe cómo implementar la `IDataGridViewEditingControl` interfaz y crear tipos personalizados derivados de `DataGridViewCell` y `DataGridViewColumn` con el fin de mostrar un <xref:System.Windows.Forms.DateTimePicker> controlar cuando una celda está en modo de edición.</span><span class="sxs-lookup"><span data-stu-id="af1fd-118">Describes how to implement the `IDataGridViewEditingControl` interface and create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to display a <xref:System.Windows.Forms.DateTimePicker> control when a cell is in edit mode.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="af1fd-119">Referencia</span><span class="sxs-lookup"><span data-stu-id="af1fd-119">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="af1fd-120">Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="af1fd-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <span data-ttu-id="af1fd-121">Proporciona documentación de referencia para la <xref:System.Windows.Forms.DataGridViewCell> clase.</span><span class="sxs-lookup"><span data-stu-id="af1fd-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCell> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <span data-ttu-id="af1fd-122">Proporciona documentación de referencia para la <xref:System.Windows.Forms.DataGridViewRow> clase.</span><span class="sxs-lookup"><span data-stu-id="af1fd-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewRow> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <span data-ttu-id="af1fd-123">Proporciona documentación de referencia para la <xref:System.Windows.Forms.DataGridViewColumn> clase.</span><span class="sxs-lookup"><span data-stu-id="af1fd-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 <span data-ttu-id="af1fd-124">Proporciona documentación de referencia para el <xref:System.Windows.Forms.IDataGridViewEditingControl> interfaz.</span><span class="sxs-lookup"><span data-stu-id="af1fd-124">Provides reference documentation for the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="af1fd-125">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="af1fd-125">Related Sections</span></span>  
 [<span data-ttu-id="af1fd-126">Estilo y formato básicos del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af1fd-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="af1fd-127">Proporciona temas que describen cómo modificar la apariencia básica del control y el formato de presentación de los datos de celda.</span><span class="sxs-lookup"><span data-stu-id="af1fd-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af1fd-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="af1fd-128">See also</span></span>
- [<span data-ttu-id="af1fd-129">DataGridView (control)</span><span class="sxs-lookup"><span data-stu-id="af1fd-129">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
- [<span data-ttu-id="af1fd-130">Tipos de columnas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af1fd-130">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
