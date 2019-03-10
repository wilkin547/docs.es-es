---
title: Filtrar Cambiar el borde y los estilos de línea de cuadrícula en el Control DataGridView de Windows Forms
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
ms.openlocfilehash: b4984dca6fb7dc8575b00758f0d61d9ff011e1ca
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703378"
---
# <a name="how-to-change-the-border-and-gridline-styles-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="69e23-102">Filtrar Cambiar el borde y los estilos de línea de cuadrícula en el Control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="69e23-102">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="69e23-103">Con el <xref:System.Windows.Forms.DataGridView> control, puede personalizar la apariencia de borde del control y de las líneas de cuadrícula para mejorar la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="69e23-103">With the <xref:System.Windows.Forms.DataGridView> control, you can customize the appearance of the control's border and gridlines to improve the user experience.</span></span> <span data-ttu-id="69e23-104">Puede modificar el color de línea de cuadrícula y el estilo de borde del control además de los estilos de borde para las celdas del control.</span><span class="sxs-lookup"><span data-stu-id="69e23-104">You can modify the gridline color and the control border style in addition to the border styles for the cells within the control.</span></span> <span data-ttu-id="69e23-105">También puede aplicar estilos de borde de celda diferentes para las celdas normales, las celdas de encabezado de fila y las celdas de encabezado de columna.</span><span class="sxs-lookup"><span data-stu-id="69e23-105">You can also apply different cell border styles for ordinary cells, row header cells, and column header cells.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69e23-106">El color de línea de cuadrícula solo se usa con el <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>, <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal>, y <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> valores de la <xref:System.Windows.Forms.DataGridViewCellBorderStyle> enumeración y el <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> valor de la <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> enumeración.</span><span class="sxs-lookup"><span data-stu-id="69e23-106">The gridline color is used only with the <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>, <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal>, and <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> values of the <xref:System.Windows.Forms.DataGridViewCellBorderStyle> enumeration and the <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> value of the <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> enumeration.</span></span> <span data-ttu-id="69e23-107">Los demás valores de estas enumeraciones utilizan los colores especificados por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="69e23-107">The other values of these enumerations use colors specified by the operating system.</span></span> <span data-ttu-id="69e23-108">Además, cuando los estilos visuales están habilitados en Windows XP y la familia Windows Server 2003 a través de la <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> método, el <xref:System.Windows.Forms.DataGridView.GridColor%2A> no se utiliza el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="69e23-108">Additionally, when visual styles are enabled on Windows XP and the Windows Server 2003 family through the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method, the <xref:System.Windows.Forms.DataGridView.GridColor%2A> property value is not used.</span></span>  
  
### <a name="to-change-the-gridline-color-programmatically"></a><span data-ttu-id="69e23-109">Para cambiar el color de línea de cuadrícula mediante programación</span><span class="sxs-lookup"><span data-stu-id="69e23-109">To change the gridline color programmatically</span></span>  
  
-   <span data-ttu-id="69e23-110">Establecer la propiedad <xref:System.Windows.Forms.DataGridView.GridColor%2A>.</span><span class="sxs-lookup"><span data-stu-id="69e23-110">Set the <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#031)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#031)]  
  
### <a name="to-change-the-border-style-of-the-entire-datagridview-control-programmatically"></a><span data-ttu-id="69e23-111">Para cambiar el estilo de borde de todo el control DataGridView mediante programación</span><span class="sxs-lookup"><span data-stu-id="69e23-111">To change the border style of the entire DataGridView control programmatically</span></span>  
  
-   <span data-ttu-id="69e23-112">Establezca la propiedad <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> en uno de los valores de enumeración <xref:System.Windows.Forms.BorderStyle>.</span><span class="sxs-lookup"><span data-stu-id="69e23-112">Set the <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> property to one of the <xref:System.Windows.Forms.BorderStyle> enumeration values.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#032)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#032)]  
  
### <a name="to-change-the-border-styles-for-datagridview-cells-programmatically"></a><span data-ttu-id="69e23-113">Para cambiar los estilos de borde para las celdas de DataGridView mediante programación</span><span class="sxs-lookup"><span data-stu-id="69e23-113">To change the border styles for DataGridView cells programmatically</span></span>  
  
-   <span data-ttu-id="69e23-114">Establecer el <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>, y <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> propiedades.</span><span class="sxs-lookup"><span data-stu-id="69e23-114">Set the <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>, and <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> properties.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#033)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#033)]  
  
## <a name="example"></a><span data-ttu-id="69e23-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="69e23-115">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#030)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#030)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="69e23-116">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="69e23-116">Compiling the Code</span></span>  
 <span data-ttu-id="69e23-117">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="69e23-117">This example requires:</span></span>  
  
-   <span data-ttu-id="69e23-118">Un control <xref:System.Windows.Forms.DataGridView> llamado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="69e23-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="69e23-119">Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> y <xref:System.Drawing?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="69e23-119">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Drawing?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69e23-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="69e23-120">See also</span></span>
- <xref:System.Windows.Forms.BorderStyle>
- <xref:System.Windows.Forms.DataGridView.BorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.GridColor%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellBorderStyle>
- <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>
- [<span data-ttu-id="69e23-121">Estilo y formato básicos del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="69e23-121">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
