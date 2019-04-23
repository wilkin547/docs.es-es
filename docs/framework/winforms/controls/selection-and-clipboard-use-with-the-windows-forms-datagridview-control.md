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
ms.openlocfilehash: 1836fbc1887082ca685c49bef2bc42bdb167578f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59105864"
---
# <a name="selection-and-clipboard-use-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="f0f3a-102">Selección y uso del Portapapeles con el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f0f3a-102">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="f0f3a-103">El `DataGridView` control proporciona una variedad de opciones para configurar cómo los usuarios pueden seleccionar celdas, filas y columnas.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-103">The `DataGridView` control provides you with a variety of options for configuring how users can select cells, rows, and columns.</span></span> <span data-ttu-id="f0f3a-104">Por ejemplo, puede habilitar selección única o múltiple, selección de filas o columnas cuando los usuarios, haga clic en las celdas completas o selección de filas o columnas completas solo cuando los usuarios, haga clic en los encabezados, lo que permite también la selección de celda.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-104">For example, you can enable single or multiple selection, selection of whole rows or columns when users click cells, or selection of whole rows or columns only when users click their headers, which enables cell selection as well.</span></span> <span data-ttu-id="f0f3a-105">Si desea proporcionar su propia interfaz de usuario para la selección, se puede deshabilitar la selección ordinaria y controlar todas las selecciones mediante programación.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-105">If you want to provide your own user interface for selection, you can disable ordinary selection and handle all selection programmatically.</span></span> <span data-ttu-id="f0f3a-106">Además, puede habilitar que los usuarios copien los valores seleccionados en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-106">Additionally, you can enable users to copy the selected values to the Clipboard.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f0f3a-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f0f3a-107">In This Section</span></span>  
 [<span data-ttu-id="f0f3a-108">Modos de selección en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f0f3a-108">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="f0f3a-109">Describe las opciones de usuario y la selección de programación en el control.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-109">Describes the options for user and programmatic selection in the control.</span></span>  
  
 [<span data-ttu-id="f0f3a-110">Cómo: Establecer el modo de selección del Control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f0f3a-110">How to: Set the Selection Mode of the Windows Forms DataGridView Control</span></span>](how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="f0f3a-111">Describe cómo configurar el control de selección de fila única cuando un usuario hace clic en una celda.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-111">Describes how to configure the control for single-row selection when a user clicks a cell.</span></span>  
  
 [<span data-ttu-id="f0f3a-112">Cómo: Obtener las celdas seleccionadas, filas y columnas en el Control DataGridView de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="f0f3a-112">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](selected-cells-rows-and-columns-datagridview.md)  
 <span data-ttu-id="f0f3a-113">Describe cómo trabajar con las recopilaciones seleccionadas de la celda, fila y columna.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-113">Describes how to work with the selected cell, row, and column collections.</span></span>  
  
 [<span data-ttu-id="f0f3a-114">Cómo: Permitir que los usuarios copien varias celdas en el Portapapeles desde el Control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f0f3a-114">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>](enable-users-to-copy-multiple-cells-to-the-clipboard-datagridview.md)  
 <span data-ttu-id="f0f3a-115">Describe cómo habilitar la compatibilidad con el Portapapeles en el control.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-115">Describes how to enable Clipboard support in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f0f3a-116">Referencia</span><span class="sxs-lookup"><span data-stu-id="f0f3a-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="f0f3a-117">Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="f0f3a-118">Proporciona documentación de referencia para el <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>  
 <span data-ttu-id="f0f3a-119">Proporciona documentación de referencia para el <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedCellCollection>  
 <span data-ttu-id="f0f3a-120">Proporciona documentación de referencia para la <xref:System.Windows.Forms.DataGridViewSelectedCellCollection> clase.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedCellCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedRowCollection>  
 <span data-ttu-id="f0f3a-121">Proporciona documentación de referencia para la <xref:System.Windows.Forms.DataGridViewSelectedRowCollection> clase.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedRowCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection>  
 <span data-ttu-id="f0f3a-122">Proporciona documentación de referencia para la <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> clase.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0f3a-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0f3a-123">See also</span></span>

- [<span data-ttu-id="f0f3a-124">DataGridView (control)</span><span class="sxs-lookup"><span data-stu-id="f0f3a-124">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="f0f3a-125">Control predeterminado de teclado y mouse en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f0f3a-125">Default Keyboard and Mouse Handling in the Windows Forms DataGridView Control</span></span>](default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
