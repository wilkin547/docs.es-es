---
title: Agregar información sobre herramientas a celdas individuales en el control DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], adding to data grids
- DataGridView control [Windows Forms], adding tooltips
- data grids [Windows Forms], adding tooltips
ms.assetid: 2a81f9de-d58b-4ea8-bc0b-8d93c2f4cf78
ms.openlocfilehash: ac86db5fa27a95adb20888cd59b5e236941d9177
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732179"
---
# <a name="how-to-add-tooltips-to-individual-cells-in-a-windows-forms-datagridview-control"></a><span data-ttu-id="30f3a-102">Cómo: Agregar información sobre herramientas a celdas individuales en un control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="30f3a-102">How to: Add ToolTips to Individual Cells in a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="30f3a-103">De forma predeterminada, la información sobre herramientas se usa para mostrar los valores de <xref:System.Windows.Forms.DataGridView> celdas que son demasiado pequeñas para mostrar todo su contenido.</span><span class="sxs-lookup"><span data-stu-id="30f3a-103">By default, ToolTips are used to display the values of <xref:System.Windows.Forms.DataGridView> cells that are too small to show their entire contents.</span></span> <span data-ttu-id="30f3a-104">Sin embargo, puede invalidar este comportamiento para establecer valores de texto de información sobre herramientas para celdas individuales.</span><span class="sxs-lookup"><span data-stu-id="30f3a-104">You can override this behavior, however, to set ToolTip-text values for individual cells.</span></span> <span data-ttu-id="30f3a-105">Esto resulta útil para mostrar a los usuarios información adicional sobre una celda o para proporcionar a los usuarios una descripción alternativa del contenido de la celda.</span><span class="sxs-lookup"><span data-stu-id="30f3a-105">This is useful to display to users additional information about a cell or to provide to users an alternate description of the cell contents.</span></span> <span data-ttu-id="30f3a-106">Por ejemplo, si tiene una fila que muestra los iconos de estado, es posible que desee proporcionar explicaciones de texto mediante la información sobre herramientas.</span><span class="sxs-lookup"><span data-stu-id="30f3a-106">For example, if you have a row that displays status icons, you may want to provide text explanations using ToolTips.</span></span>  
  
 <span data-ttu-id="30f3a-107">También puede deshabilitar la visualización de la información sobre herramientas en el nivel de celda si establece la propiedad <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> en `false`.</span><span class="sxs-lookup"><span data-stu-id="30f3a-107">You can also disable the display of cell-level ToolTips by setting the <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> property to `false`.</span></span>  
  
### <a name="to-add-a-tooltip-to-a-cell"></a><span data-ttu-id="30f3a-108">Para agregar una información sobre herramientas a una celda</span><span class="sxs-lookup"><span data-stu-id="30f3a-108">To add a ToolTip to a cell</span></span>  
  
- <span data-ttu-id="30f3a-109">Establecer la propiedad <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="30f3a-109">Set the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="30f3a-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="30f3a-110">Compiling the Code</span></span>  
  
- <span data-ttu-id="30f3a-111">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="30f3a-111">This example requires:</span></span>  
  
- <span data-ttu-id="30f3a-112">Un control de <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1` que contiene una columna denominada `Rating` para mostrar valores de cadena de uno a cuatro símbolos de asterisco ("\*").</span><span class="sxs-lookup"><span data-stu-id="30f3a-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `Rating` for displaying string values of one through four asterisk ("\*") symbols.</span></span> <span data-ttu-id="30f3a-113">El evento <xref:System.Windows.Forms.DataGridView.CellFormatting> del control debe estar asociado con el método de control de eventos que se muestra en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="30f3a-113">The <xref:System.Windows.Forms.DataGridView.CellFormatting> event of the control must be associated with the event handler method shown in the example.</span></span>  
  
- <span data-ttu-id="30f3a-114">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="30f3a-114">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="30f3a-115">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="30f3a-115">Robust Programming</span></span>  
 <span data-ttu-id="30f3a-116">Al enlazar el control de <xref:System.Windows.Forms.DataGridView> a un origen de datos externo o proporcionar su propio origen de datos mediante la implementación del modo virtual, pueden producirse problemas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="30f3a-116">When you bind the <xref:System.Windows.Forms.DataGridView> control to an external data source or provide your own data source by implementing virtual mode, you might encounter performance issues.</span></span> <span data-ttu-id="30f3a-117">Para evitar una reducción del rendimiento al trabajar con grandes cantidades de datos, controle el evento <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> en lugar de establecer la propiedad <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> de varias celdas.</span><span class="sxs-lookup"><span data-stu-id="30f3a-117">To avoid a performance penalty when working with large amounts of data, handle the <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> event rather than setting the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> property of multiple cells.</span></span> <span data-ttu-id="30f3a-118">Al controlar este evento, al obtener el valor de una celda <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> propiedad, se genera el evento y se devuelve el valor de la propiedad <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> tal y como se especifica en el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="30f3a-118">When you handle this event, getting the value of a cell <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> property raises the event and returns the value of the <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> property as specified in the event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30f3a-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="30f3a-119">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>
- [<span data-ttu-id="30f3a-120">Programar con celdas, filas y columnas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="30f3a-120">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)
