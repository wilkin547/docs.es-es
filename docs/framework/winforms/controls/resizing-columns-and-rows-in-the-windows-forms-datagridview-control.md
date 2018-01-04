---
title: "Cambiar el tamaño de columnas y filas en el control DataGridView de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], sizing rows and columns
- columns [Windows Forms], resizing in grids
- data grids [Windows Forms], resizing columns and rows
ms.assetid: 7532764d-e5c1-4943-a08b-6377a722d3b6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c1c11ca487003e57a499b3ff46178350e6aad404
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="resizing-columns-and-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="f33c1-102">Cambiar el tamaño de columnas y filas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f33c1-102">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="f33c1-103">El `DataGridView` control proporciona numerosas opciones para personalizar el comportamiento de ajuste de tamaño de sus columnas y filas.</span><span class="sxs-lookup"><span data-stu-id="f33c1-103">The `DataGridView` control provides numerous options for customizing the sizing behavior of its columns and rows.</span></span> <span data-ttu-id="f33c1-104">Por lo general, `DataGridView` celdas no cambian de tamaño en función de su contenido.</span><span class="sxs-lookup"><span data-stu-id="f33c1-104">Typically, `DataGridView` cells do not resize based on their contents.</span></span> <span data-ttu-id="f33c1-105">En su lugar, recorta cualquier valor para mostrar que es mayor que la celda.</span><span class="sxs-lookup"><span data-stu-id="f33c1-105">Instead, they clip any display value that is larger than the cell.</span></span> <span data-ttu-id="f33c1-106">Si el contenido se puede mostrar como una cadena, la celda muestra en una información sobre herramientas.</span><span class="sxs-lookup"><span data-stu-id="f33c1-106">If the content can be displayed as a string, the cell displays it in a ToolTip.</span></span>  
  
 <span data-ttu-id="f33c1-107">De forma predeterminada, los usuarios pueden arrastrar divisores de encabezado con el mouse para mostrar más información, fila y columna.</span><span class="sxs-lookup"><span data-stu-id="f33c1-107">By default, users can drag row, column, and header dividers with the mouse to show more information.</span></span> <span data-ttu-id="f33c1-108">Los usuarios pueden hacer doble clic en un divisor para cambiar automáticamente el tamaño de la banda de fila, columna o encabezado asociada en función de su contenido.</span><span class="sxs-lookup"><span data-stu-id="f33c1-108">Users can also double-click a divider to automatically resize the associated row, column, or header band based on its contents.</span></span>  
  
 <span data-ttu-id="f33c1-109">El `DataGridView` control proporciona propiedades, métodos y eventos que le permiten personalizar o deshabilitar todos estos comportamientos dirigidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="f33c1-109">The `DataGridView` control provides properties, methods, and events that enable you to customize or disable all of these user-directed behaviors.</span></span> <span data-ttu-id="f33c1-110">Además, puede cambiar mediante programación el tamaño de filas, columnas y encabezados para ajustar su contenido, o puede configurarlos para automáticamente de tamaño cuando cambie su contenido.</span><span class="sxs-lookup"><span data-stu-id="f33c1-110">Additionally, you can programmatically resize rows, columns, and headers to fit their contents, or you can configure them to automatically resize themselves whenever their contents change.</span></span> <span data-ttu-id="f33c1-111">También puede configurar las columnas para dividir automáticamente el ancho disponible del control en proporción que se especifique.</span><span class="sxs-lookup"><span data-stu-id="f33c1-111">You can also configure columns to automatically divide the available width of the control in proportions that you specify.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f33c1-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f33c1-112">In This Section</span></span>  
 [<span data-ttu-id="f33c1-113">Opciones de ajuste de tamaño en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f33c1-113">Sizing Options in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="f33c1-114">Describe las opciones de ajuste de tamaño filas, columnas y encabezados.</span><span class="sxs-lookup"><span data-stu-id="f33c1-114">Describes the options for sizing rows, columns, and headers.</span></span> <span data-ttu-id="f33c1-115">También proporciona información detallada sobre los métodos y propiedades relacionados con el ajuste de tamaño y se describen los escenarios de uso comunes.</span><span class="sxs-lookup"><span data-stu-id="f33c1-115">Also provides details on sizing-related properties and methods, and describes common usage scenarios.</span></span>  
  
 [<span data-ttu-id="f33c1-116">Modo de relleno de columnas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f33c1-116">Column Fill Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="f33c1-117">Describe el modo de relleno de columna en detalle y proporciona código de demostración que puede utilizar para experimentar con el modo de relleno de columna y otros modos.</span><span class="sxs-lookup"><span data-stu-id="f33c1-117">Describes column fill mode in detail, and provides demonstration code that you can use to experiment with column fill mode and other modes.</span></span>  
  
 [<span data-ttu-id="f33c1-118">Establecer modos de cambio de tamaño para el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f33c1-118">How to: Set the Sizing Modes of the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="f33c1-119">Describe cómo configurar los modos de ajuste de tamaño para fines comunes.</span><span class="sxs-lookup"><span data-stu-id="f33c1-119">Describes how to configure the sizing modes for common purposes.</span></span>  
  
 [<span data-ttu-id="f33c1-120">Cambiar mediante programación el tamaño de las celdas para ajustar el contenido en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f33c1-120">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programmatically-resize-cells-to-fit-content-in-the-datagrid.md)  
 <span data-ttu-id="f33c1-121">Proporciona código de demostración que puede utilizar para experimentar con el cambio de tamaño mediante programación.</span><span class="sxs-lookup"><span data-stu-id="f33c1-121">Provides demonstration code that you can use to experiment with programmatic resizing.</span></span>  
  
 [<span data-ttu-id="f33c1-122">Cambiar automáticamente el tamaño de las celdas cuando se modifica el contenido en un control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f33c1-122">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/automatically-resize-cells-when-content-changes-in-the-datagrid.md)  
 <span data-ttu-id="f33c1-123">Proporciona código de demostración que puede utilizar para experimentar con los modos de ajuste automático de tamaño.</span><span class="sxs-lookup"><span data-stu-id="f33c1-123">Provides demonstration code that you can use to experiment with automatic sizing modes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f33c1-124">Referencia</span><span class="sxs-lookup"><span data-stu-id="f33c1-124">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="f33c1-125">Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="f33c1-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f33c1-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f33c1-126">See Also</span></span>  
 [<span data-ttu-id="f33c1-127">DataGridView (control)</span><span class="sxs-lookup"><span data-stu-id="f33c1-127">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
