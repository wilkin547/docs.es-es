---
title: Cambiar el tamaño de columnas y filas en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], sizing rows and columns
- columns [Windows Forms], resizing in grids
- data grids [Windows Forms], resizing columns and rows
ms.assetid: 7532764d-e5c1-4943-a08b-6377a722d3b6
ms.openlocfilehash: e1fa2d57cfb2cd374d691fe03a0e0bdbd3ad7141
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59138117"
---
# <a name="resizing-columns-and-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="e5208-102">Cambiar el tamaño de columnas y filas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e5208-102">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="e5208-103">El `DataGridView` ofrece numerosas opciones para personalizar el comportamiento de ajuste de tamaño de sus columnas y filas.</span><span class="sxs-lookup"><span data-stu-id="e5208-103">The `DataGridView` control provides numerous options for customizing the sizing behavior of its columns and rows.</span></span> <span data-ttu-id="e5208-104">Por lo general, `DataGridView` celdas no cambian de tamaño según su contenido.</span><span class="sxs-lookup"><span data-stu-id="e5208-104">Typically, `DataGridView` cells do not resize based on their contents.</span></span> <span data-ttu-id="e5208-105">En su lugar, recorta cualquier valor para mostrar que es mayor que la celda.</span><span class="sxs-lookup"><span data-stu-id="e5208-105">Instead, they clip any display value that is larger than the cell.</span></span> <span data-ttu-id="e5208-106">Si el contenido se puede mostrar como una cadena, la celda muestra en una información sobre herramientas.</span><span class="sxs-lookup"><span data-stu-id="e5208-106">If the content can be displayed as a string, the cell displays it in a ToolTip.</span></span>  
  
 <span data-ttu-id="e5208-107">De forma predeterminada, los usuarios pueden arrastrar los divisores de encabezado con el mouse para mostrar más información, columna y fila.</span><span class="sxs-lookup"><span data-stu-id="e5208-107">By default, users can drag row, column, and header dividers with the mouse to show more information.</span></span> <span data-ttu-id="e5208-108">Los usuarios pueden hacer doble clic en un divisor para ajustar automáticamente la banda de encabezado, columna o fila asociada en función de su contenido.</span><span class="sxs-lookup"><span data-stu-id="e5208-108">Users can also double-click a divider to automatically resize the associated row, column, or header band based on its contents.</span></span>  
  
 <span data-ttu-id="e5208-109">El `DataGridView` control proporciona propiedades, métodos y eventos que le permiten personalizar o deshabilitar todos estos comportamientos dirigido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="e5208-109">The `DataGridView` control provides properties, methods, and events that enable you to customize or disable all of these user-directed behaviors.</span></span> <span data-ttu-id="e5208-110">Además, puede cambiar mediante programación el tamaño de filas, columnas y encabezados para ajustar su contenido, o puede configurarlos para automáticamente de tamaño automáticamente cuando cambie su contenido.</span><span class="sxs-lookup"><span data-stu-id="e5208-110">Additionally, you can programmatically resize rows, columns, and headers to fit their contents, or you can configure them to automatically resize themselves whenever their contents change.</span></span> <span data-ttu-id="e5208-111">También puede configurar columnas para dividir automáticamente el ancho disponible del control en proporciones que especifique.</span><span class="sxs-lookup"><span data-stu-id="e5208-111">You can also configure columns to automatically divide the available width of the control in proportions that you specify.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e5208-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e5208-112">In This Section</span></span>  
 [<span data-ttu-id="e5208-113">Opciones de ajuste de tamaño en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e5208-113">Sizing Options in the Windows Forms DataGridView Control</span></span>](sizing-options-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e5208-114">Describe las opciones de ajuste de tamaño filas, columnas y encabezados.</span><span class="sxs-lookup"><span data-stu-id="e5208-114">Describes the options for sizing rows, columns, and headers.</span></span> <span data-ttu-id="e5208-115">También proporciona detalles sobre los métodos y propiedades relacionadas con el ajuste de tamaño y se describen escenarios de uso comunes.</span><span class="sxs-lookup"><span data-stu-id="e5208-115">Also provides details on sizing-related properties and methods, and describes common usage scenarios.</span></span>  
  
 [<span data-ttu-id="e5208-116">Modo de relleno de columnas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e5208-116">Column Fill Mode in the Windows Forms DataGridView Control</span></span>](column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e5208-117">Describe el modo de relleno de columna en detalle y proporciona código de demostración que puede usar para experimentar con el modo de relleno de columna y otros modos.</span><span class="sxs-lookup"><span data-stu-id="e5208-117">Describes column fill mode in detail, and provides demonstration code that you can use to experiment with column fill mode and other modes.</span></span>  
  
 [<span data-ttu-id="e5208-118">Cómo: Establecer modos de ajuste de tamaño del Control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e5208-118">How to: Set the Sizing Modes of the Windows Forms DataGridView Control</span></span>](how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e5208-119">Describe cómo configurar los modos de ajuste de tamaño para los propósitos comunes.</span><span class="sxs-lookup"><span data-stu-id="e5208-119">Describes how to configure the sizing modes for common purposes.</span></span>  
  
 [<span data-ttu-id="e5208-120">Cómo: Cambiar el tamaño de las celdas para ajustar el contenido en el Control DataGridView de Windows Forms mediante programación</span><span class="sxs-lookup"><span data-stu-id="e5208-120">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>](programmatically-resize-cells-to-fit-content-in-the-datagrid.md)  
 <span data-ttu-id="e5208-121">Proporciona código de demostración que puede usar para experimentar con el cambio de tamaño mediante programación.</span><span class="sxs-lookup"><span data-stu-id="e5208-121">Provides demonstration code that you can use to experiment with programmatic resizing.</span></span>  
  
 [<span data-ttu-id="e5208-122">Cómo: Las celdas de tamaño automáticamente cuando cambia el contenido en el Control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e5208-122">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>](automatically-resize-cells-when-content-changes-in-the-datagrid.md)  
 <span data-ttu-id="e5208-123">Proporciona código de demostración que puede usar para experimentar con los modos de ajuste de tamaño automático.</span><span class="sxs-lookup"><span data-stu-id="e5208-123">Provides demonstration code that you can use to experiment with automatic sizing modes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e5208-124">Referencia</span><span class="sxs-lookup"><span data-stu-id="e5208-124">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="e5208-125">Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="e5208-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5208-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5208-126">See also</span></span>

- [<span data-ttu-id="e5208-127">DataGridView (control)</span><span class="sxs-lookup"><span data-stu-id="e5208-127">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
