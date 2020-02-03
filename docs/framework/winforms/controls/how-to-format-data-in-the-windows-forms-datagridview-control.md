---
title: Dar formato a los datos en el control DataGridView
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
ms.openlocfilehash: 9ee2869cf4085b5acfdf1f8c440151be506dbe3e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736780"
---
# <a name="how-to-format-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="40b3c-102">Cómo: Dar formato a datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="40b3c-102">How to: Format Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="40b3c-103">En los procedimientos siguientes se muestra el formato básico de los valores de celda mediante la <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> propiedad de un control <xref:System.Windows.Forms.DataGridView> y de las columnas específicas de un control.</span><span class="sxs-lookup"><span data-stu-id="40b3c-103">The following procedures demonstrate basic formatting of cell values using the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> property of a <xref:System.Windows.Forms.DataGridView> control and of specific columns in a control.</span></span> <span data-ttu-id="40b3c-104">Para obtener información sobre el formato de datos avanzado, vea [Cómo: personalizar el formato de datos en el control DataGridView Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="40b3c-104">For information about advanced data formatting, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-format-currency-and-date-values"></a><span data-ttu-id="40b3c-105">Para dar formato a los valores de fecha y moneda</span><span class="sxs-lookup"><span data-stu-id="40b3c-105">To format currency and date values</span></span>  
  
- <span data-ttu-id="40b3c-106">Establezca la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> de un <xref:System.Windows.Forms.DataGridViewCellStyle>.</span><span class="sxs-lookup"><span data-stu-id="40b3c-106">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="40b3c-107">En el ejemplo de código siguiente se establece el formato de columnas específicas mediante la <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> propiedad de las columnas.</span><span class="sxs-lookup"><span data-stu-id="40b3c-107">The following code example sets the format for specific columns using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the columns.</span></span> <span data-ttu-id="40b3c-108">Los valores de la columna `UnitPrice` aparecen en el formato de moneda específico de la referencia cultural actual, con valores negativos entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="40b3c-108">Values in the `UnitPrice` column appear in the current culture-specific currency format, with negative values surrounded by parentheses.</span></span> <span data-ttu-id="40b3c-109">Los valores de la columna `ShipDate` aparecen en el formato de fecha corta específico de la referencia cultural actual.</span><span class="sxs-lookup"><span data-stu-id="40b3c-109">Values in the `ShipDate` column appear in the current culture-specific short date format.</span></span> <span data-ttu-id="40b3c-110">Para obtener más información sobre los valores de <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A>, vea [aplicar formato a tipos](../../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="40b3c-110">For more information about <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> values, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### <a name="to-customize-the-display-of-null-database-values"></a><span data-ttu-id="40b3c-111">Para personalizar la presentación de valores de base de datos null</span><span class="sxs-lookup"><span data-stu-id="40b3c-111">To customize the display of null database values</span></span>  
  
- <span data-ttu-id="40b3c-112">Establezca la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> de un <xref:System.Windows.Forms.DataGridViewCellStyle>.</span><span class="sxs-lookup"><span data-stu-id="40b3c-112">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="40b3c-113">En el ejemplo de código siguiente se usa la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> para mostrar "sin entrada" en todas las celdas que contienen valores iguales a <xref:System.DBNull.Value?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="40b3c-113">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to display "no entry" in all cells containing values equal to <xref:System.DBNull.Value?displayProperty=nameWithType>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### <a name="to-enable-wordwrap-in-text-based-cells"></a><span data-ttu-id="40b3c-114">Para habilitar WordWrap en celdas basadas en texto</span><span class="sxs-lookup"><span data-stu-id="40b3c-114">To enable wordwrap in text-based cells</span></span>  
  
- <span data-ttu-id="40b3c-115">Establezca la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> de una <xref:System.Windows.Forms.DataGridViewCellStyle> en uno de los valores de enumeración <xref:System.Windows.Forms.DataGridViewTriState>.</span><span class="sxs-lookup"><span data-stu-id="40b3c-115">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewTriState> enumeration values.</span></span> <span data-ttu-id="40b3c-116">En el ejemplo de código siguiente se usa la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> para establecer el modo de ajuste para todo el control.</span><span class="sxs-lookup"><span data-stu-id="40b3c-116">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to set the wrap mode for the entire control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### <a name="to-specify-the-text-alignment-of-datagridview-cells"></a><span data-ttu-id="40b3c-117">Para especificar la alineación del texto de las celdas de DataGridView</span><span class="sxs-lookup"><span data-stu-id="40b3c-117">To specify the text alignment of DataGridView cells</span></span>  
  
- <span data-ttu-id="40b3c-118">Establezca la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> de una <xref:System.Windows.Forms.DataGridViewCellStyle> en uno de los valores de enumeración <xref:System.Windows.Forms.DataGridViewContentAlignment>.</span><span class="sxs-lookup"><span data-stu-id="40b3c-118">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewContentAlignment> enumeration values.</span></span> <span data-ttu-id="40b3c-119">En el ejemplo de código siguiente se establece la alineación de una columna concreta utilizando la propiedad <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> de la columna.</span><span class="sxs-lookup"><span data-stu-id="40b3c-119">The following code example sets the alignment for a specific column using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the column.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## <a name="example"></a><span data-ttu-id="40b3c-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="40b3c-120">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="40b3c-121">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="40b3c-121">Compiling the Code</span></span>  
 <span data-ttu-id="40b3c-122">Estos ejemplos requieren:</span><span class="sxs-lookup"><span data-stu-id="40b3c-122">These examples require:</span></span>  
  
- <span data-ttu-id="40b3c-123">Un control de <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1` que contiene una columna denominada `UnitPrice`, una columna denominada `ShipDate`y una columna denominada `CustomerName`.</span><span class="sxs-lookup"><span data-stu-id="40b3c-123">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `UnitPrice`, a column named `ShipDate`, and a column named `CustomerName`.</span></span>  
  
- <span data-ttu-id="40b3c-124">Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="40b3c-124">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="40b3c-125">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="40b3c-125">Robust Programming</span></span>  
 <span data-ttu-id="40b3c-126">Para obtener la máxima escalabilidad, debe compartir <xref:System.Windows.Forms.DataGridViewCellStyle> objetos en varias filas, columnas o celdas que usen los mismos estilos en lugar de establecer las propiedades de estilo para cada elemento por separado.</span><span class="sxs-lookup"><span data-stu-id="40b3c-126">For maximum scalability, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles rather than setting the style properties for each element separately.</span></span> <span data-ttu-id="40b3c-127">Para obtener más información, consulte [Procedimientos recomendados para ajustar la escala del control DataGridView en Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="40b3c-127">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40b3c-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="40b3c-128">See also</span></span>

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [<span data-ttu-id="40b3c-129">Estilo y formato básicos del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="40b3c-129">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="40b3c-130">Estilos de celda en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="40b3c-130">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="40b3c-131">Formato de datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="40b3c-131">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="40b3c-132">Personalizar el formato de los datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="40b3c-132">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="40b3c-133">Aplicación de formato a tipos</span><span class="sxs-lookup"><span data-stu-id="40b3c-133">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
