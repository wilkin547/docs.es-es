---
title: Cambiar los estilos de borde y de línea de cuadrícula en el control DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gridlines [Windows Forms], changing styles
- data grids [Windows Forms], changing gridline styles
- DataGridView control [Windows Forms], border styles
- data grids [Windows Forms], changing border styles
- DataGridView control [Windows Forms], gridline styles
ms.assetid: 2f413c7a-4025-4171-8e3a-66ef908ea583
ms.openlocfilehash: 918102a87ee29a3d3b78d6e6eedce57237135a51
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744700"
---
# <a name="how-to-change-the-border-and-gridline-styles-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="34946-102">Cómo: Cambiar los estilos de borde y línea de la cuadrícula en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="34946-102">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="34946-103">Con el control <xref:System.Windows.Forms.DataGridView>, puede personalizar la apariencia del borde y las líneas de cuadrícula del control para mejorar la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="34946-103">With the <xref:System.Windows.Forms.DataGridView> control, you can customize the appearance of the control's border and gridlines to improve the user experience.</span></span> <span data-ttu-id="34946-104">Puede modificar el color de la cuadrícula y el estilo de borde del control, además de los estilos de borde de las celdas del control.</span><span class="sxs-lookup"><span data-stu-id="34946-104">You can modify the gridline color and the control border style in addition to the border styles for the cells within the control.</span></span> <span data-ttu-id="34946-105">También puede aplicar distintos estilos de borde de celda para celdas normales, celdas de encabezado de fila y celdas de encabezado de columna.</span><span class="sxs-lookup"><span data-stu-id="34946-105">You can also apply different cell border styles for ordinary cells, row header cells, and column header cells.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="34946-106">El color de la cuadrícula se usa solo con los valores <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>, <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal>y <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> de la enumeración <xref:System.Windows.Forms.DataGridViewCellBorderStyle> y el valor <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> de la enumeración <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>.</span><span class="sxs-lookup"><span data-stu-id="34946-106">The gridline color is used only with the <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>, <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal>, and <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> values of the <xref:System.Windows.Forms.DataGridViewCellBorderStyle> enumeration and the <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> value of the <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> enumeration.</span></span> <span data-ttu-id="34946-107">Los demás valores de estas enumeraciones usan los colores especificados por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="34946-107">The other values of these enumerations use colors specified by the operating system.</span></span> <span data-ttu-id="34946-108">Además, cuando los estilos visuales están habilitados en Windows XP y en la familia de Windows Server 2003 a través del método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>, no se utiliza el valor de la propiedad <xref:System.Windows.Forms.DataGridView.GridColor%2A>.</span><span class="sxs-lookup"><span data-stu-id="34946-108">Additionally, when visual styles are enabled on Windows XP and the Windows Server 2003 family through the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method, the <xref:System.Windows.Forms.DataGridView.GridColor%2A> property value is not used.</span></span>  
  
### <a name="to-change-the-gridline-color-programmatically"></a><span data-ttu-id="34946-109">Para cambiar el color de la línea de cuadrícula mediante programación</span><span class="sxs-lookup"><span data-stu-id="34946-109">To change the gridline color programmatically</span></span>  
  
- <span data-ttu-id="34946-110">Establecer la propiedad <xref:System.Windows.Forms.DataGridView.GridColor%2A>.</span><span class="sxs-lookup"><span data-stu-id="34946-110">Set the <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#031)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#031)]  
  
### <a name="to-change-the-border-style-of-the-entire-datagridview-control-programmatically"></a><span data-ttu-id="34946-111">Para cambiar mediante programación el estilo de borde del control DataGridView completo</span><span class="sxs-lookup"><span data-stu-id="34946-111">To change the border style of the entire DataGridView control programmatically</span></span>  
  
- <span data-ttu-id="34946-112">Establezca la propiedad <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> en uno de los valores de enumeración <xref:System.Windows.Forms.BorderStyle>.</span><span class="sxs-lookup"><span data-stu-id="34946-112">Set the <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> property to one of the <xref:System.Windows.Forms.BorderStyle> enumeration values.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#032)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#032)]  
  
### <a name="to-change-the-border-styles-for-datagridview-cells-programmatically"></a><span data-ttu-id="34946-113">Para cambiar mediante programación los estilos de borde de las celdas de DataGridView</span><span class="sxs-lookup"><span data-stu-id="34946-113">To change the border styles for DataGridView cells programmatically</span></span>  
  
- <span data-ttu-id="34946-114">Establezca las propiedades <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>y <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> .</span><span class="sxs-lookup"><span data-stu-id="34946-114">Set the <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>, and <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> properties.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#033)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#033)]  
  
## <a name="example"></a><span data-ttu-id="34946-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34946-115">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#030)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#030)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="34946-116">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="34946-116">Compiling the Code</span></span>  
 <span data-ttu-id="34946-117">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="34946-117">This example requires:</span></span>  
  
- <span data-ttu-id="34946-118">Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="34946-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="34946-119">Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> y <xref:System.Drawing?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="34946-119">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Drawing?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34946-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="34946-120">See also</span></span>

- <xref:System.Windows.Forms.BorderStyle>
- <xref:System.Windows.Forms.DataGridView.BorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.GridColor%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellBorderStyle>
- <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>
- [<span data-ttu-id="34946-121">Estilo y formato básicos del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="34946-121">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
