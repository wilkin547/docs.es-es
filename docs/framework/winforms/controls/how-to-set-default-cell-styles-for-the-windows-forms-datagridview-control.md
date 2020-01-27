---
title: Establecer estilos de celda predeterminados para el control DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: 1aaaca43-5340-447e-99c0-9177d9776aa1
ms.openlocfilehash: 6b2d7de671e48ae8f55987c262e15717138b3fb4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744867"
---
# <a name="how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="4cee3-102">Cómo: Establecer estilos de celda predeterminados para el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4cee3-102">How to: Set Default Cell Styles for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="4cee3-103">Con el control <xref:System.Windows.Forms.DataGridView>, puede especificar los estilos de celda predeterminados para todo el control y para columnas y filas específicas.</span><span class="sxs-lookup"><span data-stu-id="4cee3-103">With the <xref:System.Windows.Forms.DataGridView> control, you can specify default cell styles for the entire control and for specific columns and rows.</span></span> <span data-ttu-id="4cee3-104">Estos valores predeterminados filtran desde el nivel de control al nivel de columna, después al nivel de fila y, después, al nivel de celda.</span><span class="sxs-lookup"><span data-stu-id="4cee3-104">These defaults filter down from the control level to the column level, then to the row level, then to the cell level.</span></span> <span data-ttu-id="4cee3-105">Si una determinada propiedad <xref:System.Windows.Forms.DataGridViewCellStyle> no está establecida en el nivel de celda, se usa el valor de propiedad predeterminado en el nivel de fila.</span><span class="sxs-lookup"><span data-stu-id="4cee3-105">If a particular <xref:System.Windows.Forms.DataGridViewCellStyle> property is not set at the cell level, the default property setting at the row level is used.</span></span> <span data-ttu-id="4cee3-106">Si la propiedad tampoco está establecida en el nivel de fila, se usa el valor de columna predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4cee3-106">If the property is also not set at the row level, the default column setting is used.</span></span> <span data-ttu-id="4cee3-107">Por último, si la propiedad tampoco está establecida en el nivel de columna, se usa el valor predeterminado de <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="4cee3-107">Finally, if the property is also not set at the column level, the default <xref:System.Windows.Forms.DataGridView> setting is used.</span></span> <span data-ttu-id="4cee3-108">Con esta configuración, puede evitar tener que duplicar los valores de propiedad en varios niveles.</span><span class="sxs-lookup"><span data-stu-id="4cee3-108">With this setting, you can avoid having to duplicate the property settings at multiple levels.</span></span> <span data-ttu-id="4cee3-109">En cada nivel, simplemente hay que especificar los estilos que difieren de los niveles situados por encima de él.</span><span class="sxs-lookup"><span data-stu-id="4cee3-109">At each level, simply specify the styles that differ from the levels above it.</span></span> <span data-ttu-id="4cee3-110">Para obtener más información, vea [estilos de celda en el control DataGridView de Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="4cee3-110">For more information, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="4cee3-111">Visual Studio es altamente compatible con esta tarea.</span><span class="sxs-lookup"><span data-stu-id="4cee3-111">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="4cee3-112">Consulte también [Cómo: establecer estilos de celda y formatos de datos predeterminados para el control DataGridView Windows Forms mediante el diseñador](default-cell-styles-datagridview.md).</span><span class="sxs-lookup"><span data-stu-id="4cee3-112">Also see [How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer](default-cell-styles-datagridview.md).</span></span>  
  
### <a name="to-set-the-default-cell-styles-programmatically"></a><span data-ttu-id="4cee3-113">Para establecer los estilos de celda predeterminados mediante programación</span><span class="sxs-lookup"><span data-stu-id="4cee3-113">To set the default cell styles programmatically</span></span>  
  
1. <span data-ttu-id="4cee3-114">Establezca las propiedades del <xref:System.Windows.Forms.DataGridViewCellStyle> recuperado a través de la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4cee3-114">Set the properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> retrieved through the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#141](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#141)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#141](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#141)]  
  
2. <span data-ttu-id="4cee3-115">Cree e inicialice los nuevos objetos <xref:System.Windows.Forms.DataGridViewCellStyle> para que los usen varias filas y columnas.</span><span class="sxs-lookup"><span data-stu-id="4cee3-115">Create and initialize new <xref:System.Windows.Forms.DataGridViewCellStyle> objects for use by multiple rows and columns.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#142](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#142)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#142](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#142)]  
  
3. <span data-ttu-id="4cee3-116">Establezca la propiedad `DefaultCellStyle` de filas y columnas específicas.</span><span class="sxs-lookup"><span data-stu-id="4cee3-116">Set the `DefaultCellStyle` property of specific rows and columns.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#143](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#143)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#143](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#143)]  
  
## <a name="example"></a><span data-ttu-id="4cee3-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4cee3-117">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#140)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#140)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4cee3-118">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="4cee3-118">Compiling the Code</span></span>  
 <span data-ttu-id="4cee3-119">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="4cee3-119">This example requires:</span></span>  
  
- <span data-ttu-id="4cee3-120">Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="4cee3-120">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="4cee3-121">Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4cee3-121">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4cee3-122">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="4cee3-122">Robust Programming</span></span>  
 <span data-ttu-id="4cee3-123">Para lograr la máxima escalabilidad al trabajar con conjuntos de datos muy grandes, se recomienda compartir objetos <xref:System.Windows.Forms.DataGridViewCellStyle> entre varias filas, columnas o celdas que usen los mismos estilos, en lugar de establecer las propiedades de estilo de cada elemento individual por separado.</span><span class="sxs-lookup"><span data-stu-id="4cee3-123">To achieve maximum scalability when you work with very large data sets, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles, rather than set the style properties for individual elements separately.</span></span> <span data-ttu-id="4cee3-124">Además, debe crear filas compartidas y acceder a ellas mediante la propiedad <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4cee3-124">Additionally, you should create shared rows and access them by using the <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="4cee3-125">Para obtener más información, vea [prácticas recomendadas para escalar el control DataGridView Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="4cee3-125">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cee3-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="4cee3-126">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- [<span data-ttu-id="4cee3-127">Estilo y formato básicos del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4cee3-127">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="4cee3-128">Estilos de celda en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4cee3-128">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="4cee3-129">Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4cee3-129">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="4cee3-130">Establecer estilos de fila alternos para el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4cee3-130">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)
