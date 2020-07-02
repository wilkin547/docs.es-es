---
title: Dar formato a los datos en el control DataGridView
description: Obtenga información sobre cómo dar formato a los valores de celda mediante la propiedad DefaultCellStyle de un control DataGridView Windows Forms y de columnas específicas de un control.
ms.date: 03/30/2017
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
ms.openlocfilehash: d6105c1d1120876f854332e7a10106cc1caf6276
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622814"
---
# <a name="how-to-format-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="4e619-103">Procedimiento para dar formato a datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4e619-103">How to: Format Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="4e619-104">Los procedimientos siguientes muestran el formato básico de los valores de celda mediante la <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> propiedad de un <xref:System.Windows.Forms.DataGridView> control y de las columnas específicas de un control.</span><span class="sxs-lookup"><span data-stu-id="4e619-104">The following procedures demonstrate basic formatting of cell values using the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> property of a <xref:System.Windows.Forms.DataGridView> control and of specific columns in a control.</span></span> <span data-ttu-id="4e619-105">Para obtener información sobre el formato de datos avanzado, vea [Cómo: personalizar el formato de datos en el control DataGridView Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="4e619-105">For information about advanced data formatting, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-format-currency-and-date-values"></a><span data-ttu-id="4e619-106">Para dar formato a los valores de fecha y moneda</span><span class="sxs-lookup"><span data-stu-id="4e619-106">To format currency and date values</span></span>  
  
- <span data-ttu-id="4e619-107">Establezca la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> de un <xref:System.Windows.Forms.DataGridViewCellStyle>.</span><span class="sxs-lookup"><span data-stu-id="4e619-107">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="4e619-108">En el ejemplo de código siguiente se establece el formato de columnas específicas mediante la <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> propiedad de las columnas.</span><span class="sxs-lookup"><span data-stu-id="4e619-108">The following code example sets the format for specific columns using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the columns.</span></span> <span data-ttu-id="4e619-109">Los valores de la `UnitPrice` columna aparecen en el formato de moneda específico de la referencia cultural actual, con valores negativos entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="4e619-109">Values in the `UnitPrice` column appear in the current culture-specific currency format, with negative values surrounded by parentheses.</span></span> <span data-ttu-id="4e619-110">Los valores de la `ShipDate` columna aparecen en el formato de fecha corta específico de la referencia cultural actual.</span><span class="sxs-lookup"><span data-stu-id="4e619-110">Values in the `ShipDate` column appear in the current culture-specific short date format.</span></span> <span data-ttu-id="4e619-111">Para obtener más información sobre <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> los valores, vea [aplicar formato a tipos](../../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="4e619-111">For more information about <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> values, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### <a name="to-customize-the-display-of-null-database-values"></a><span data-ttu-id="4e619-112">Para personalizar la presentación de valores de base de datos null</span><span class="sxs-lookup"><span data-stu-id="4e619-112">To customize the display of null database values</span></span>  
  
- <span data-ttu-id="4e619-113">Establezca la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> de un <xref:System.Windows.Forms.DataGridViewCellStyle>.</span><span class="sxs-lookup"><span data-stu-id="4e619-113">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="4e619-114">En el ejemplo de código siguiente <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> se usa la propiedad para mostrar "sin entrada" en todas las celdas que contienen valores iguales a <xref:System.DBNull.Value?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="4e619-114">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to display "no entry" in all cells containing values equal to <xref:System.DBNull.Value?displayProperty=nameWithType>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### <a name="to-enable-wordwrap-in-text-based-cells"></a><span data-ttu-id="4e619-115">Para habilitar WordWrap en celdas basadas en texto</span><span class="sxs-lookup"><span data-stu-id="4e619-115">To enable wordwrap in text-based cells</span></span>  
  
- <span data-ttu-id="4e619-116">Establezca la <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> propiedad de <xref:System.Windows.Forms.DataGridViewCellStyle> en uno de los <xref:System.Windows.Forms.DataGridViewTriState> valores de enumeración.</span><span class="sxs-lookup"><span data-stu-id="4e619-116">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewTriState> enumeration values.</span></span> <span data-ttu-id="4e619-117">En el ejemplo de código siguiente <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> se usa la propiedad para establecer el modo de ajuste para todo el control.</span><span class="sxs-lookup"><span data-stu-id="4e619-117">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to set the wrap mode for the entire control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### <a name="to-specify-the-text-alignment-of-datagridview-cells"></a><span data-ttu-id="4e619-118">Para especificar la alineación del texto de las celdas de DataGridView</span><span class="sxs-lookup"><span data-stu-id="4e619-118">To specify the text alignment of DataGridView cells</span></span>  
  
- <span data-ttu-id="4e619-119">Establezca la <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> propiedad de <xref:System.Windows.Forms.DataGridViewCellStyle> en uno de los <xref:System.Windows.Forms.DataGridViewContentAlignment> valores de enumeración.</span><span class="sxs-lookup"><span data-stu-id="4e619-119">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewContentAlignment> enumeration values.</span></span> <span data-ttu-id="4e619-120">En el ejemplo de código siguiente se establece la alineación de una columna concreta mediante la <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> propiedad de la columna.</span><span class="sxs-lookup"><span data-stu-id="4e619-120">The following code example sets the alignment for a specific column using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the column.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## <a name="example"></a><span data-ttu-id="4e619-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4e619-121">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4e619-122">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="4e619-122">Compiling the Code</span></span>  
 <span data-ttu-id="4e619-123">Estos ejemplos requieren:</span><span class="sxs-lookup"><span data-stu-id="4e619-123">These examples require:</span></span>  
  
- <span data-ttu-id="4e619-124">Un <xref:System.Windows.Forms.DataGridView> control denominado `dataGridView1` que contiene una columna denominada `UnitPrice` , una columna denominada `ShipDate` y una columna denominada `CustomerName` .</span><span class="sxs-lookup"><span data-stu-id="4e619-124">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `UnitPrice`, a column named `ShipDate`, and a column named `CustomerName`.</span></span>  
  
- <span data-ttu-id="4e619-125">Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4e619-125">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4e619-126">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="4e619-126">Robust Programming</span></span>  
 <span data-ttu-id="4e619-127">Para obtener la máxima escalabilidad, debe compartir <xref:System.Windows.Forms.DataGridViewCellStyle> objetos entre varias filas, columnas o celdas que usen los mismos estilos en lugar de establecer las propiedades de estilo para cada elemento por separado.</span><span class="sxs-lookup"><span data-stu-id="4e619-127">For maximum scalability, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles rather than setting the style properties for each element separately.</span></span> <span data-ttu-id="4e619-128">Para obtener más información, consulte [Procedimientos recomendados para ajustar la escala del control DataGridView en Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="4e619-128">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e619-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e619-129">See also</span></span>

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [<span data-ttu-id="4e619-130">Estilo y formato básicos del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4e619-130">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="4e619-131">Estilos de celda en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4e619-131">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="4e619-132">Formato de datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4e619-132">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="4e619-133">Procedimiento para personalizar el formato de los datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4e619-133">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="4e619-134">Aplicación de formato a tipos</span><span class="sxs-lookup"><span data-stu-id="4e619-134">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
