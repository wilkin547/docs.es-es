---
title: "Cómo: Dar formato a datos en el control DataGridView de formularios Windows Forms"
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
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in DataGridView control
- data grids [Windows Forms], enabling wordwrap
- currency values [Windows Forms], formatting in data grids
- data grids [Windows Forms], currency values
- data grids [Windows Forms], formatting data
- data grids [Windows Forms], text alignment
- data grids [Windows Forms], date values
- cells [Windows Forms], text alignment
ms.assetid: 8c33543c-9c08-4636-a65a-fdf714a529b7
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 49d5172b2638a7ac3a6a7bf005932ba4b3f9aba3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-format-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="d36eb-102">Cómo: Dar formato a datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d36eb-102">How to: Format Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="d36eb-103">Los procedimientos siguientes muestran el formato básico de los valores de celda mediante la <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> propiedad de un <xref:System.Windows.Forms.DataGridView> control y de columnas concretas de un control.</span><span class="sxs-lookup"><span data-stu-id="d36eb-103">The following procedures demonstrate basic formatting of cell values using the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> property of a <xref:System.Windows.Forms.DataGridView> control and of specific columns in a control.</span></span> <span data-ttu-id="d36eb-104">Para obtener información sobre los formatos de datos avanzados, consulte [Cómo: personalizar el formato de datos en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="d36eb-104">For information about advanced data formatting, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-format-currency-and-date-values"></a><span data-ttu-id="d36eb-105">Para dar formato a moneda y valores de fecha</span><span class="sxs-lookup"><span data-stu-id="d36eb-105">To format currency and date values</span></span>  
  
-   <span data-ttu-id="d36eb-106">Establezca la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> de un <xref:System.Windows.Forms.DataGridViewCellStyle>.</span><span class="sxs-lookup"><span data-stu-id="d36eb-106">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="d36eb-107">En el ejemplo de código siguiente se establece el formato de columnas específicas mediante la <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> propiedad de las columnas.</span><span class="sxs-lookup"><span data-stu-id="d36eb-107">The following code example sets the format for specific columns using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the columns.</span></span> <span data-ttu-id="d36eb-108">Los valores en la `UnitPrice` columna aparecen en el formato de moneda específica de la referencia cultural actual, con valores negativos entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="d36eb-108">Values in the `UnitPrice` column appear in the current culture-specific currency format, with negative values surrounded by parentheses.</span></span> <span data-ttu-id="d36eb-109">Los valores en la `ShipDate` columna aparece en el formato de fecha corta de específicos de la referencia cultural actual.</span><span class="sxs-lookup"><span data-stu-id="d36eb-109">Values in the `ShipDate` column appear in the current culture-specific short date format.</span></span> <span data-ttu-id="d36eb-110">Para obtener más información acerca de <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> valores, consulte [Formatting Types](../../../../docs/standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="d36eb-110">For more information about <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> values, see [Formatting Types](../../../../docs/standard/base-types/formatting-types.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### <a name="to-customize-the-display-of-null-database-values"></a><span data-ttu-id="d36eb-111">Para personalizar la presentación de valores null de la base de datos</span><span class="sxs-lookup"><span data-stu-id="d36eb-111">To customize the display of null database values</span></span>  
  
-   <span data-ttu-id="d36eb-112">Establezca la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> de un <xref:System.Windows.Forms.DataGridViewCellStyle>.</span><span class="sxs-lookup"><span data-stu-id="d36eb-112">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="d36eb-113">El siguiente ejemplo de código utiliza el <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> propiedad para no mostrar "ninguna entrada" en todas las celdas que contienen valores iguales a <xref:System.DBNull.Value?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d36eb-113">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to display "no entry" in all cells containing values equal to <xref:System.DBNull.Value?displayProperty=nameWithType>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### <a name="to-enable-wordwrap-in-text-based-cells"></a><span data-ttu-id="d36eb-114">Para habilitar el ajuste de línea en celdas basadas en texto</span><span class="sxs-lookup"><span data-stu-id="d36eb-114">To enable wordwrap in text-based cells</span></span>  
  
-   <span data-ttu-id="d36eb-115">Establecer el <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> propiedad de un <xref:System.Windows.Forms.DataGridViewCellStyle> a uno de los <xref:System.Windows.Forms.DataGridViewTriState> valores de enumeración.</span><span class="sxs-lookup"><span data-stu-id="d36eb-115">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewTriState> enumeration values.</span></span> <span data-ttu-id="d36eb-116">El siguiente ejemplo de código utiliza el <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> propiedad para establecer el modo de ajuste para todo el control.</span><span class="sxs-lookup"><span data-stu-id="d36eb-116">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to set the wrap mode for the entire control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### <a name="to-specify-the-text-alignment-of-datagridview-cells"></a><span data-ttu-id="d36eb-117">Para especificar la alineación del texto de las celdas de DataGridView</span><span class="sxs-lookup"><span data-stu-id="d36eb-117">To specify the text alignment of DataGridView cells</span></span>  
  
-   <span data-ttu-id="d36eb-118">Establecer el <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> propiedad de un <xref:System.Windows.Forms.DataGridViewCellStyle> a uno de los <xref:System.Windows.Forms.DataGridViewContentAlignment> valores de enumeración.</span><span class="sxs-lookup"><span data-stu-id="d36eb-118">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewContentAlignment> enumeration values.</span></span> <span data-ttu-id="d36eb-119">En el ejemplo de código siguiente se establece la alineación de una columna específica con la <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> propiedad de la columna.</span><span class="sxs-lookup"><span data-stu-id="d36eb-119">The following code example sets the alignment for a specific column using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the column.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## <a name="example"></a><span data-ttu-id="d36eb-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d36eb-120">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d36eb-121">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="d36eb-121">Compiling the Code</span></span>  
 <span data-ttu-id="d36eb-122">Para estos ejemplos se necesita:</span><span class="sxs-lookup"><span data-stu-id="d36eb-122">These examples require:</span></span>  
  
-   <span data-ttu-id="d36eb-123">A <xref:System.Windows.Forms.DataGridView> control denominado `dataGridView1` que contiene una columna denominada `UnitPrice`, una columna denominada `ShipDate`y una columna denominada `CustomerName`.</span><span class="sxs-lookup"><span data-stu-id="d36eb-123">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `UnitPrice`, a column named `ShipDate`, and a column named `CustomerName`.</span></span>  
  
-   <span data-ttu-id="d36eb-124">Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d36eb-124">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="d36eb-125">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="d36eb-125">Robust Programming</span></span>  
 <span data-ttu-id="d36eb-126">Para conseguir la máxima escalabilidad, se recomienda compartir <xref:System.Windows.Forms.DataGridViewCellStyle> objetos a través de varias filas, columnas o celdas que usen los mismos estilos, en lugar de establecer las propiedades de estilo para cada elemento por separado.</span><span class="sxs-lookup"><span data-stu-id="d36eb-126">For maximum scalability, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles rather than setting the style properties for each element separately.</span></span> <span data-ttu-id="d36eb-127">Para obtener más información, consulte [procedimientos recomendados para ajustar la escala del DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="d36eb-127">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d36eb-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="d36eb-128">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 [<span data-ttu-id="d36eb-129">Estilo y formato básicos del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d36eb-129">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="d36eb-130">Estilos de celda en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d36eb-130">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="d36eb-131">Formato de datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d36eb-131">Data Formatting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="d36eb-132">Personalizar el formato de los datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d36eb-132">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="d36eb-133">Aplicación de formato a tipos</span><span class="sxs-lookup"><span data-stu-id="d36eb-133">Formatting Types</span></span>](../../../../docs/standard/base-types/formatting-types.md)
