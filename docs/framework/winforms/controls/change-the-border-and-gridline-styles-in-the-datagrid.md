---
title: Procedimiento para cambiar los estilos de borde y línea de la cuadrícula en el control DataGridView de formularios Windows Forms
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
ms.openlocfilehash: ebeca5f933eac4da2bf3d4f300866fd2ff52b32a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917671"
---
# <a name="how-to-change-the-border-and-gridline-styles-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="028e8-102">Procedimiento para cambiar los estilos de borde y línea de la cuadrícula en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="028e8-102">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="028e8-103">Con el <xref:System.Windows.Forms.DataGridView> control, puede personalizar la apariencia del borde y las líneas de cuadrícula del control para mejorar la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="028e8-103">With the <xref:System.Windows.Forms.DataGridView> control, you can customize the appearance of the control's border and gridlines to improve the user experience.</span></span> <span data-ttu-id="028e8-104">Puede modificar el color de la cuadrícula y el estilo de borde del control, además de los estilos de borde de las celdas del control.</span><span class="sxs-lookup"><span data-stu-id="028e8-104">You can modify the gridline color and the control border style in addition to the border styles for the cells within the control.</span></span> <span data-ttu-id="028e8-105">También puede aplicar distintos estilos de borde de celda para celdas normales, celdas de encabezado de fila y celdas de encabezado de columna.</span><span class="sxs-lookup"><span data-stu-id="028e8-105">You can also apply different cell border styles for ordinary cells, row header cells, and column header cells.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="028e8-106">El color de la cuadrícula se usa solo <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>con <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal>los valores <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> , y de <xref:System.Windows.Forms.DataGridViewCellBorderStyle> la enumeración <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> y el valor <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="028e8-106">The gridline color is used only with the <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>, <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal>, and <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> values of the <xref:System.Windows.Forms.DataGridViewCellBorderStyle> enumeration and the <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> value of the <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> enumeration.</span></span> <span data-ttu-id="028e8-107">Los demás valores de estas enumeraciones usan los colores especificados por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="028e8-107">The other values of these enumerations use colors specified by the operating system.</span></span> <span data-ttu-id="028e8-108">Además, cuando los estilos visuales están habilitados en Windows XP y en la familia de Windows <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> Server 2003 a <xref:System.Windows.Forms.DataGridView.GridColor%2A> través del método, no se utiliza el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="028e8-108">Additionally, when visual styles are enabled on Windows XP and the Windows Server 2003 family through the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method, the <xref:System.Windows.Forms.DataGridView.GridColor%2A> property value is not used.</span></span>  
  
### <a name="to-change-the-gridline-color-programmatically"></a><span data-ttu-id="028e8-109">Para cambiar el color de la línea de cuadrícula mediante programación</span><span class="sxs-lookup"><span data-stu-id="028e8-109">To change the gridline color programmatically</span></span>  
  
- <span data-ttu-id="028e8-110">Establecer la propiedad <xref:System.Windows.Forms.DataGridView.GridColor%2A>.</span><span class="sxs-lookup"><span data-stu-id="028e8-110">Set the <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#031)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#031)]  
  
### <a name="to-change-the-border-style-of-the-entire-datagridview-control-programmatically"></a><span data-ttu-id="028e8-111">Para cambiar mediante programación el estilo de borde del control DataGridView completo</span><span class="sxs-lookup"><span data-stu-id="028e8-111">To change the border style of the entire DataGridView control programmatically</span></span>  
  
- <span data-ttu-id="028e8-112">Establezca la propiedad <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> en uno de los valores de enumeración <xref:System.Windows.Forms.BorderStyle>.</span><span class="sxs-lookup"><span data-stu-id="028e8-112">Set the <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> property to one of the <xref:System.Windows.Forms.BorderStyle> enumeration values.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#032)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#032)]  
  
### <a name="to-change-the-border-styles-for-datagridview-cells-programmatically"></a><span data-ttu-id="028e8-113">Para cambiar mediante programación los estilos de borde de las celdas de DataGridView</span><span class="sxs-lookup"><span data-stu-id="028e8-113">To change the border styles for DataGridView cells programmatically</span></span>  
  
- <span data-ttu-id="028e8-114">Establezca las <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>propiedades <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>, y <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> .</span><span class="sxs-lookup"><span data-stu-id="028e8-114">Set the <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>, and <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> properties.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#033)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#033)]  
  
## <a name="example"></a><span data-ttu-id="028e8-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="028e8-115">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#030)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#030)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="028e8-116">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="028e8-116">Compiling the Code</span></span>  
 <span data-ttu-id="028e8-117">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="028e8-117">This example requires:</span></span>  
  
- <span data-ttu-id="028e8-118">Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="028e8-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="028e8-119">Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> y <xref:System.Drawing?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="028e8-119">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Drawing?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="028e8-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="028e8-120">See also</span></span>

- <xref:System.Windows.Forms.BorderStyle>
- <xref:System.Windows.Forms.DataGridView.BorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.GridColor%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellBorderStyle>
- <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>
- [<span data-ttu-id="028e8-121">Estilo y formato básicos del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="028e8-121">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
