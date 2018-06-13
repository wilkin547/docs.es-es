---
title: Selección y uso del Portapapeles con el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], Clipboard use
- cells [Windows Forms], selecting in grids
- Clipboard [Windows Forms], in DataGridView control
- selection [Windows Forms], in DataGridView control
- data grids [Windows Forms], selecting cells
- DataGridView control [Windows Forms], selecting cells
ms.assetid: 82cffcad-8b30-4897-bddb-c3a79d751b83
ms.openlocfilehash: c777366124a3cc5f43df8efca54fc366245bcb75
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537647"
---
# <a name="selection-and-clipboard-use-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="87909-102">Selección y uso del Portapapeles con el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="87909-102">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="87909-103">El `DataGridView` control proporciona una variedad de opciones para configurar cómo los usuarios pueden seleccionar celdas, filas y columnas.</span><span class="sxs-lookup"><span data-stu-id="87909-103">The `DataGridView` control provides you with a variety of options for configuring how users can select cells, rows, and columns.</span></span> <span data-ttu-id="87909-104">Por ejemplo, puede habilitar selección única o múltiple, selección de filas o columnas cuando los usuarios, haga clic en celdas completas o selección de filas o columnas completas sólo cuando los usuarios, haga clic en sus encabezados, que permite también la selección de celdas.</span><span class="sxs-lookup"><span data-stu-id="87909-104">For example, you can enable single or multiple selection, selection of whole rows or columns when users click cells, or selection of whole rows or columns only when users click their headers, which enables cell selection as well.</span></span> <span data-ttu-id="87909-105">Si desea proporcionar su propia interfaz de usuario para la selección, puede deshabilitar la selección ordinaria y controlar mediante programación toda la selección.</span><span class="sxs-lookup"><span data-stu-id="87909-105">If you want to provide your own user interface for selection, you can disable ordinary selection and handle all selection programmatically.</span></span> <span data-ttu-id="87909-106">Además, puede permitir a los usuarios copiar los valores seleccionados en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="87909-106">Additionally, you can enable users to copy the selected values to the Clipboard.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="87909-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="87909-107">In This Section</span></span>  
 [<span data-ttu-id="87909-108">Modos de selección en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="87909-108">Selection Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="87909-109">Describe las opciones de usuario y la selección mediante programación en el control.</span><span class="sxs-lookup"><span data-stu-id="87909-109">Describes the options for user and programmatic selection in the control.</span></span>  
  
 [<span data-ttu-id="87909-110">Establecer el modelo de selección del control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="87909-110">How to: Set the Selection Mode of the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="87909-111">Describe cómo configurar el control de selección de fila única cuando un usuario hace clic en una celda.</span><span class="sxs-lookup"><span data-stu-id="87909-111">Describes how to configure the control for single-row selection when a user clicks a cell.</span></span>  
  
 [<span data-ttu-id="87909-112">Obtener las celdas, filas y columnas seleccionadas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="87909-112">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selected-cells-rows-and-columns-datagridview.md)  
 <span data-ttu-id="87909-113">Describe cómo trabajar con las recopilaciones de celdas, filas y columnas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="87909-113">Describes how to work with the selected cell, row, and column collections.</span></span>  
  
 [<span data-ttu-id="87909-114">Permitir que los usuarios copien varias celdas en el Portapapeles desde el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="87909-114">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/enable-users-to-copy-multiple-cells-to-the-clipboard-datagridview.md)  
 <span data-ttu-id="87909-115">Describe cómo habilitar la compatibilidad de Portapapeles en el control.</span><span class="sxs-lookup"><span data-stu-id="87909-115">Describes how to enable Clipboard support in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="87909-116">Referencia</span><span class="sxs-lookup"><span data-stu-id="87909-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="87909-117">Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="87909-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="87909-118">Proporciona documentación de referencia para el <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="87909-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>  
 <span data-ttu-id="87909-119">Proporciona documentación de referencia para el <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="87909-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedCellCollection>  
 <span data-ttu-id="87909-120">Proporciona documentación de referencia para la <xref:System.Windows.Forms.DataGridViewSelectedCellCollection> clase.</span><span class="sxs-lookup"><span data-stu-id="87909-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedCellCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedRowCollection>  
 <span data-ttu-id="87909-121">Proporciona documentación de referencia para la <xref:System.Windows.Forms.DataGridViewSelectedRowCollection> clase.</span><span class="sxs-lookup"><span data-stu-id="87909-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedRowCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection>  
 <span data-ttu-id="87909-122">Proporciona documentación de referencia para la <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> clase.</span><span class="sxs-lookup"><span data-stu-id="87909-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87909-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="87909-123">See Also</span></span>  
 [<span data-ttu-id="87909-124">DataGridView (control)</span><span class="sxs-lookup"><span data-stu-id="87909-124">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="87909-125">Control predeterminado de teclado y mouse en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="87909-125">Default Keyboard and Mouse Handling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
