---
title: "Cómo: Establecer estilos de celda predeterminados para el control DataGridView de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: 1aaaca43-5340-447e-99c0-9177d9776aa1
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cd55034ee97b6e13da8a8a0bdadb8c191ba16ae2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="99f4a-102">Cómo: Establecer estilos de celda predeterminados para el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="99f4a-102">How to: Set Default Cell Styles for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="99f4a-103">Con el control <xref:System.Windows.Forms.DataGridView>, puede especificar los estilos de celda predeterminados para todo el control y para columnas y filas específicas.</span><span class="sxs-lookup"><span data-stu-id="99f4a-103">With the <xref:System.Windows.Forms.DataGridView> control, you can specify default cell styles for the entire control and for specific columns and rows.</span></span> <span data-ttu-id="99f4a-104">Estos valores predeterminados filtran desde el nivel de control al nivel de columna, después al nivel de fila y, después, al nivel de celda.</span><span class="sxs-lookup"><span data-stu-id="99f4a-104">These defaults filter down from the control level to the column level, then to the row level, then to the cell level.</span></span> <span data-ttu-id="99f4a-105">Si una determinada propiedad <xref:System.Windows.Forms.DataGridViewCellStyle> no está establecida en el nivel de celda, se usa el valor de propiedad predeterminado en el nivel de fila.</span><span class="sxs-lookup"><span data-stu-id="99f4a-105">If a particular <xref:System.Windows.Forms.DataGridViewCellStyle> property is not set at the cell level, the default property setting at the row level is used.</span></span> <span data-ttu-id="99f4a-106">Si la propiedad tampoco está establecida en el nivel de fila, se usa el valor de columna predeterminado.</span><span class="sxs-lookup"><span data-stu-id="99f4a-106">If the property is also not set at the row level, the default column setting is used.</span></span> <span data-ttu-id="99f4a-107">Por último, si la propiedad tampoco está establecida en el nivel de columna, se usa el valor predeterminado de <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="99f4a-107">Finally, if the property is also not set at the column level, the default <xref:System.Windows.Forms.DataGridView> setting is used.</span></span> <span data-ttu-id="99f4a-108">Con esta configuración, puede evitar tener que duplicar los valores de propiedad en varios niveles.</span><span class="sxs-lookup"><span data-stu-id="99f4a-108">With this setting, you can avoid having to duplicate the property settings at multiple levels.</span></span> <span data-ttu-id="99f4a-109">En cada nivel, simplemente hay que especificar los estilos que difieren de los niveles situados por encima de él.</span><span class="sxs-lookup"><span data-stu-id="99f4a-109">At each level, simply specify the styles that differ from the levels above it.</span></span> <span data-ttu-id="99f4a-110">Para obtener más información, consulte [estilos de celda en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="99f4a-110">For more information, see [Cell Styles in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="99f4a-111">Visual Studio es altamente compatible con esta tarea.</span><span class="sxs-lookup"><span data-stu-id="99f4a-111">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="99f4a-112">Consulte también [Cómo: establecer estilos de celda predeterminados y formatos de datos para el Control Windows Forms DataGridView mediante el diseñador](http://msdn.microsoft.com/library/95y5fz2x\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="99f4a-112">Also see [How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer](http://msdn.microsoft.com/library/95y5fz2x\(v=vs.110\)).</span></span>  
  
### <a name="to-set-the-default-cell-styles-programmatically"></a><span data-ttu-id="99f4a-113">Para establecer los estilos de celda predeterminados mediante programación</span><span class="sxs-lookup"><span data-stu-id="99f4a-113">To set the default cell styles programmatically</span></span>  
  
1.  <span data-ttu-id="99f4a-114">Establezca las propiedades del <xref:System.Windows.Forms.DataGridViewCellStyle> recuperado a través de la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="99f4a-114">Set the properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> retrieved through the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#141](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#141)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#141](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#141)]  
  
2.  <span data-ttu-id="99f4a-115">Cree e inicialice los nuevos objetos <xref:System.Windows.Forms.DataGridViewCellStyle> para que los usen varias filas y columnas.</span><span class="sxs-lookup"><span data-stu-id="99f4a-115">Create and initialize new <xref:System.Windows.Forms.DataGridViewCellStyle> objects for use by multiple rows and columns.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#142](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#142)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#142](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#142)]  
  
3.  <span data-ttu-id="99f4a-116">Establezca la propiedad `DefaultCellStyle` de filas y columnas específicas.</span><span class="sxs-lookup"><span data-stu-id="99f4a-116">Set the `DefaultCellStyle` property of specific rows and columns.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#143](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#143)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#143](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#143)]  
  
## <a name="example"></a><span data-ttu-id="99f4a-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="99f4a-117">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#140)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#140)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="99f4a-118">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="99f4a-118">Compiling the Code</span></span>  
 <span data-ttu-id="99f4a-119">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="99f4a-119">This example requires:</span></span>  
  
-   <span data-ttu-id="99f4a-120">Un control <xref:System.Windows.Forms.DataGridView> llamado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="99f4a-120">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="99f4a-121">Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="99f4a-121">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="99f4a-122">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="99f4a-122">Robust Programming</span></span>  
 <span data-ttu-id="99f4a-123">Para lograr la máxima escalabilidad al trabajar con conjuntos de datos muy grandes, se recomienda compartir objetos <xref:System.Windows.Forms.DataGridViewCellStyle> entre varias filas, columnas o celdas que usen los mismos estilos, en lugar de establecer las propiedades de estilo de cada elemento individual por separado.</span><span class="sxs-lookup"><span data-stu-id="99f4a-123">To achieve maximum scalability when you work with very large data sets, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles, rather than set the style properties for individual elements separately.</span></span> <span data-ttu-id="99f4a-124">Además, debe crear filas compartidas y acceder a ellas mediante la propiedad <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="99f4a-124">Additionally, you should create shared rows and access them by using the <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="99f4a-125">Para obtener más información, consulte [procedimientos recomendados para ajustar la escala del DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="99f4a-125">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99f4a-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="99f4a-126">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="99f4a-127">Estilo y formato básicos del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="99f4a-127">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="99f4a-128">Estilos de celda en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="99f4a-128">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="99f4a-129">Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="99f4a-129">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="99f4a-130">Establecer estilos de fila alternos para el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="99f4a-130">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)
