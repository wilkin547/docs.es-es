---
title: "Cómo: Establecer estilos de fila alternos para el control DataGridView de formularios Windows Forms"
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
- DataGridView control [Windows Forms], row styles
- data grids [Windows Forms], row styles
- rows [Windows Forms], data grids
ms.assetid: 699ef759-458c-426d-ac87-7c7e71b018ae
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a31e8eb02949c0f6db487e3cd1a6976f2ed37222
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="fb2ad-102">Cómo: Establecer estilos de fila alternos para el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fb2ad-102">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="fb2ad-103">Los datos tabulares suelen presentarse a los usuarios en un formato de doble carta en el que las filas alternas tienen distintos colores de fondo.</span><span class="sxs-lookup"><span data-stu-id="fb2ad-103">Tabular data is often presented to users in a ledger-like format where alternating rows have different background colors.</span></span> <span data-ttu-id="fb2ad-104">Este formato permite a los usuarios saber fácilmente qué celdas están en cada fila, especialmente con tablas anchas que tienen muchas columnas.</span><span class="sxs-lookup"><span data-stu-id="fb2ad-104">This format makes it easier for users to tell which cells are in each row, especially with wide tables that have many columns.</span></span>  
  
 <span data-ttu-id="fb2ad-105">Con el control <xref:System.Windows.Forms.DataGridView>, puede especificar la información de estilo completa para las filas alternas.</span><span class="sxs-lookup"><span data-stu-id="fb2ad-105">With the <xref:System.Windows.Forms.DataGridView> control, you can specify complete style information for alternating rows.</span></span> <span data-ttu-id="fb2ad-106">Esto permite usar características de estilo tales como el color de primer plano y la fuente, además del color de fondo, para diferenciar las filas alternas.</span><span class="sxs-lookup"><span data-stu-id="fb2ad-106">This enables you use style characteristics like foreground color and font, in addition to background color, to differentiate alternating rows.</span></span>  
  
 <span data-ttu-id="fb2ad-107">Visual Studio es compatible con esta tarea.</span><span class="sxs-lookup"><span data-stu-id="fb2ad-107">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="fb2ad-108">Consulte también [Cómo: establecer estilos de fila alternos para el Control Windows Forms DataGridView mediante el diseñador](http://msdn.microsoft.com/library/3z9sk148\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="fb2ad-108">Also see [How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer](http://msdn.microsoft.com/library/3z9sk148\(v=vs.110\)).</span></span>  
  
### <a name="to-set-alternating-row-styles-programmatically"></a><span data-ttu-id="fb2ad-109">Para establecer estilos de fila alternos mediante programación</span><span class="sxs-lookup"><span data-stu-id="fb2ad-109">To set alternating row styles programmatically</span></span>  
  
-   <span data-ttu-id="fb2ad-110">Establezca las propiedades de los objetos <xref:System.Windows.Forms.DataGridViewCellStyle> devueltos por las propiedades <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> y <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> de <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="fb2ad-110">Set the properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> objects returned by the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> and <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> properties of the <xref:System.Windows.Forms.DataGridView>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#068](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#068)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#068](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#068)]  
  
    > [!NOTE]
    >  <span data-ttu-id="fb2ad-111">Los estilos especificados con las propiedades <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> y <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> invalidan los estilos especificados en el nivel de columna y de <xref:System.Windows.Forms.DataGridView>, pero son invalidados por los estilos establecidos en el nivel de cada fila y celda.</span><span class="sxs-lookup"><span data-stu-id="fb2ad-111">The styles specified using the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> and <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> properties override the styles specified on the column and <xref:System.Windows.Forms.DataGridView> level, but are overridden by the styles set on the individual row and cell level.</span></span> <span data-ttu-id="fb2ad-112">Para obtener más información, consulte [estilos de celda en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="fb2ad-112">For more information, see [Cell Styles in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fb2ad-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="fb2ad-113">Compiling the Code</span></span>  
 <span data-ttu-id="fb2ad-114">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="fb2ad-114">This example requires:</span></span>  
  
-   <span data-ttu-id="fb2ad-115">Un control <xref:System.Windows.Forms.DataGridView> llamado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="fb2ad-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="fb2ad-116">Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fb2ad-116">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="fb2ad-117">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="fb2ad-117">Robust Programming</span></span>  
 <span data-ttu-id="fb2ad-118">Para conseguir la máxima escalabilidad, debe compartir objetos <xref:System.Windows.Forms.DataGridViewCellStyle> entre varias filas, columnas o celdas que usen los mismos estilos, en lugar de establecer las propiedades de estilo de cada elemento por separado.</span><span class="sxs-lookup"><span data-stu-id="fb2ad-118">For maximum scalability, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles, rather than setting the style properties for each element separately.</span></span> <span data-ttu-id="fb2ad-119">Para obtener más información, consulte [procedimientos recomendados para ajustar la escala del DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="fb2ad-119">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb2ad-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb2ad-120">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 [<span data-ttu-id="fb2ad-121">Estilo y formato básicos del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fb2ad-121">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="fb2ad-122">Estilos de celda en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fb2ad-122">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="fb2ad-123">Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fb2ad-123">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="fb2ad-124">Establecer estilos de colores y fuentes en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fb2ad-124">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)
