---
title: Establecer estilos de colores y fuentes en el control DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], cell customization
- data grids [Windows Forms], customizing cells
- data grids [Windows Forms], font styles
- data grids [Windows Forms], color styles
ms.assetid: 588f2c57-d963-41b1-9c1d-d02d71818113
ms.openlocfilehash: f1ee9131cfc0b28a5f6263dcd6254d27a092cc62
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746756"
---
# <a name="how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="a28b5-102">Cómo: Establecer estilos de colores y fuentes en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a28b5-102">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="a28b5-103">Para especificar la apariencia visual de las celdas dentro de un control <xref:System.Windows.Forms.DataGridView>, establezca las propiedades de la clase <xref:System.Windows.Forms.DataGridViewCellStyle>.</span><span class="sxs-lookup"><span data-stu-id="a28b5-103">You can specify the visual appearance of cells within a <xref:System.Windows.Forms.DataGridView> control by setting properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> class.</span></span> <span data-ttu-id="a28b5-104">Puede recuperar instancias de esta clase desde distintas propiedades de la clase <xref:System.Windows.Forms.DataGridView> y sus clases complementarias, o puede crear instancias de objetos <xref:System.Windows.Forms.DataGridViewCellStyle> para la asignación de estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="a28b5-104">You can retrieve instances of this class from various properties of the <xref:System.Windows.Forms.DataGridView> class and its companion classes, or you can instantiate <xref:System.Windows.Forms.DataGridViewCellStyle> objects for assignment to these properties.</span></span>  
  
 <span data-ttu-id="a28b5-105">Los procedimientos siguientes muestran cómo realizar una personalización básica de la apariencia de las celdas mediante la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>.</span><span class="sxs-lookup"><span data-stu-id="a28b5-105">The following procedures demonstrate basic customization of cell appearance using the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> property.</span></span> <span data-ttu-id="a28b5-106">Cada celda del control hereda los estilos especificados mediante esta propiedad, a menos que se invaliden en el nivel de celda, fila o columna.</span><span class="sxs-lookup"><span data-stu-id="a28b5-106">Every cell in the control inherits the styles specified through this property unless they are overridden at the column, row, or cell level.</span></span> <span data-ttu-id="a28b5-107">Para obtener un ejemplo de herencia de estilo, vea [Cómo: establecer estilos de celda predeterminados para el control DataGridView de Windows Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="a28b5-107">For an example of style inheritance, see [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span> <span data-ttu-id="a28b5-108">Para obtener información sobre otros adicionales de la clase <xref:System.Windows.Forms.DataGridViewCellStyle>, consulte los temas de la sección Consulte también.</span><span class="sxs-lookup"><span data-stu-id="a28b5-108">For information about additional uses of the <xref:System.Windows.Forms.DataGridViewCellStyle> class, see the topics listed in the See Also section.</span></span>  
  
 <span data-ttu-id="a28b5-109">Visual Studio es altamente compatible con esta tarea.</span><span class="sxs-lookup"><span data-stu-id="a28b5-109">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="a28b5-110">Consulte también [Cómo: establecer estilos de celda y formatos de datos predeterminados para el control DataGridView Windows Forms mediante el diseñador](default-cell-styles-datagridview.md).</span><span class="sxs-lookup"><span data-stu-id="a28b5-110">Also see [How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer](default-cell-styles-datagridview.md).</span></span>  
  
### <a name="to-specify-the-font-used-by-datagridview-cells"></a><span data-ttu-id="a28b5-111">Para especificar la fuente que usan las celdas de DataGridView</span><span class="sxs-lookup"><span data-stu-id="a28b5-111">To specify the font used by DataGridView cells</span></span>  
  
- <span data-ttu-id="a28b5-112">Establezca la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> de un <xref:System.Windows.Forms.DataGridViewCellStyle>.</span><span class="sxs-lookup"><span data-stu-id="a28b5-112">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="a28b5-113">El siguiente ejemplo de código usa la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> para establecer la fuente para todo el control.</span><span class="sxs-lookup"><span data-stu-id="a28b5-113">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to set the font for the entire control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#101](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#101)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#101](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#101)]  
  
### <a name="to-specify-the-foreground-and-background-colors-of-datagridview-cells"></a><span data-ttu-id="a28b5-114">Para especificar los colores de primer plano y de fondo de las celdas de DataGridView</span><span class="sxs-lookup"><span data-stu-id="a28b5-114">To specify the foreground and background colors of DataGridView cells</span></span>  
  
- <span data-ttu-id="a28b5-115">Establezca las propiedades <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> y <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> de un <xref:System.Windows.Forms.DataGridViewCellStyle>.</span><span class="sxs-lookup"><span data-stu-id="a28b5-115">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> and <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> properties of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="a28b5-116">El siguiente ejemplo de código usa la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> para establecer estos estilos para todo el control.</span><span class="sxs-lookup"><span data-stu-id="a28b5-116">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to set these styles for the entire control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#102](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#102)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#102](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#102)]  
  
### <a name="to-specify-the-foreground-and-background-colors-of-selected-datagridview-cells"></a><span data-ttu-id="a28b5-117">Para especificar los colores de primer plano y de fondo de las celdas seleccionadas de DataGridView</span><span class="sxs-lookup"><span data-stu-id="a28b5-117">To specify the foreground and background colors of selected DataGridView cells</span></span>  
  
- <span data-ttu-id="a28b5-118">Establezca las propiedades <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A> y <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> de un <xref:System.Windows.Forms.DataGridViewCellStyle>.</span><span class="sxs-lookup"><span data-stu-id="a28b5-118">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A> and <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> properties of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="a28b5-119">El siguiente ejemplo de código usa la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> para establecer estos estilos para todo el control.</span><span class="sxs-lookup"><span data-stu-id="a28b5-119">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to set these styles for the entire control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#103](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#103)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#103](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#103)]  
  
## <a name="example"></a><span data-ttu-id="a28b5-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a28b5-120">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#100)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a28b5-121">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="a28b5-121">Compiling the Code</span></span>  
 <span data-ttu-id="a28b5-122">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="a28b5-122">This example requires:</span></span>  
  
- <span data-ttu-id="a28b5-123">Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="a28b5-123">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="a28b5-124">Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a28b5-124">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a28b5-125">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="a28b5-125">Robust Programming</span></span>  
 <span data-ttu-id="a28b5-126">Para conseguir la máxima escalabilidad, debe compartir objetos <xref:System.Windows.Forms.DataGridViewCellStyle> entre varias filas, columnas o celdas que usen los mismos estilos, en lugar de establecer las propiedades de estilo de cada elemento por separado.</span><span class="sxs-lookup"><span data-stu-id="a28b5-126">For maximum scalability, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles, rather than setting the style properties for each element separately.</span></span> <span data-ttu-id="a28b5-127">Para obtener más información, consulte [Procedimientos recomendados para ajustar la escala del control DataGridView en Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="a28b5-127">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a28b5-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a28b5-128">See also</span></span>

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [<span data-ttu-id="a28b5-129">Estilo y formato básicos del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a28b5-129">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="a28b5-130">Estilos de celda en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a28b5-130">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
