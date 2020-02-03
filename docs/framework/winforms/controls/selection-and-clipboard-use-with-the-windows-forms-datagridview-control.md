---
title: Selección y uso del Portapapeles con el control DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], Clipboard use
- cells [Windows Forms], selecting in grids
- Clipboard [Windows Forms], in DataGridView control
- selection [Windows Forms], in DataGridView control
- data grids [Windows Forms], selecting cells
- DataGridView control [Windows Forms], selecting cells
ms.assetid: 82cffcad-8b30-4897-bddb-c3a79d751b83
ms.openlocfilehash: 6993f77e8ce532d8df1bdc7e6b6abc1cc3268e49
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743060"
---
# <a name="selection-and-clipboard-use-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="2c0c9-102">Selección y uso del Portapapeles con el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2c0c9-102">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2c0c9-103">El control `DataGridView` proporciona diversas opciones para configurar el modo en que los usuarios pueden seleccionar celdas, filas y columnas.</span><span class="sxs-lookup"><span data-stu-id="2c0c9-103">The `DataGridView` control provides you with a variety of options for configuring how users can select cells, rows, and columns.</span></span> <span data-ttu-id="2c0c9-104">Por ejemplo, puede habilitar una selección única o múltiple, la selección de filas o columnas completas cuando los usuarios hacen clic en las celdas, o la selección de filas o columnas completas solo cuando los usuarios hacen clic en sus encabezados, lo que permite la selección de celdas.</span><span class="sxs-lookup"><span data-stu-id="2c0c9-104">For example, you can enable single or multiple selection, selection of whole rows or columns when users click cells, or selection of whole rows or columns only when users click their headers, which enables cell selection as well.</span></span> <span data-ttu-id="2c0c9-105">Si desea proporcionar su propia interfaz de usuario para la selección, puede deshabilitar la selección ordinaria y controlar todas las selecciones mediante programación.</span><span class="sxs-lookup"><span data-stu-id="2c0c9-105">If you want to provide your own user interface for selection, you can disable ordinary selection and handle all selection programmatically.</span></span> <span data-ttu-id="2c0c9-106">Además, puede permitir que los usuarios copien los valores seleccionados en el portapapeles.</span><span class="sxs-lookup"><span data-stu-id="2c0c9-106">Additionally, you can enable users to copy the selected values to the Clipboard.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2c0c9-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2c0c9-107">In This Section</span></span>  
 [<span data-ttu-id="2c0c9-108">Modos de selección en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2c0c9-108">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2c0c9-109">Describe las opciones de usuario y la selección mediante programación en el control.</span><span class="sxs-lookup"><span data-stu-id="2c0c9-109">Describes the options for user and programmatic selection in the control.</span></span>  
  
 [<span data-ttu-id="2c0c9-110">Establecer el modelo de selección del control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2c0c9-110">How to: Set the Selection Mode of the Windows Forms DataGridView Control</span></span>](how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2c0c9-111">Describe cómo configurar el control para la selección de fila única cuando un usuario hace clic en una celda.</span><span class="sxs-lookup"><span data-stu-id="2c0c9-111">Describes how to configure the control for single-row selection when a user clicks a cell.</span></span>  
  
 [<span data-ttu-id="2c0c9-112">Obtener las celdas, filas y columnas seleccionadas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2c0c9-112">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](selected-cells-rows-and-columns-datagridview.md)  
 <span data-ttu-id="2c0c9-113">Describe cómo trabajar con las colecciones de celda, fila y columna seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="2c0c9-113">Describes how to work with the selected cell, row, and column collections.</span></span>  
  
 [<span data-ttu-id="2c0c9-114">Permitir que los usuarios copien varias celdas en el Portapapeles desde el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2c0c9-114">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>](enable-users-to-copy-multiple-cells-to-the-clipboard-datagridview.md)  
 <span data-ttu-id="2c0c9-115">Describe cómo habilitar la compatibilidad del portapapeles en el control.</span><span class="sxs-lookup"><span data-stu-id="2c0c9-115">Describes how to enable Clipboard support in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2c0c9-116">Referencia</span><span class="sxs-lookup"><span data-stu-id="2c0c9-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="2c0c9-117">Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="2c0c9-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="2c0c9-118">Proporciona documentación de referencia para la propiedad <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="2c0c9-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>  
 <span data-ttu-id="2c0c9-119">Proporciona documentación de referencia para la propiedad <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="2c0c9-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedCellCollection>  
 <span data-ttu-id="2c0c9-120">Proporciona documentación de referencia para la clase <xref:System.Windows.Forms.DataGridViewSelectedCellCollection>.</span><span class="sxs-lookup"><span data-stu-id="2c0c9-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedCellCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedRowCollection>  
 <span data-ttu-id="2c0c9-121">Proporciona documentación de referencia para la clase <xref:System.Windows.Forms.DataGridViewSelectedRowCollection>.</span><span class="sxs-lookup"><span data-stu-id="2c0c9-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedRowCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection>  
 <span data-ttu-id="2c0c9-122">Proporciona documentación de referencia para la clase <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection>.</span><span class="sxs-lookup"><span data-stu-id="2c0c9-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c0c9-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2c0c9-123">See also</span></span>

- [<span data-ttu-id="2c0c9-124">DataGridView (control)</span><span class="sxs-lookup"><span data-stu-id="2c0c9-124">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="2c0c9-125">Control predeterminado de teclado y mouse en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2c0c9-125">Default Keyboard and Mouse Handling in the Windows Forms DataGridView Control</span></span>](default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
