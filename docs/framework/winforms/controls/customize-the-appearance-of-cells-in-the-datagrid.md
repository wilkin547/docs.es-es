---
title: Personalizar la apariencia de las celdas en el control DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
ms.openlocfilehash: 754932427a365a7b032c1ac9627d3237d1f7d0c6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744057"
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="6b00b-102">Cómo: Personalizar la apariencia de las celdas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6b00b-102">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="6b00b-103">Puede personalizar la apariencia de cualquier celda controlando el evento de <xref:System.Windows.Forms.DataGridView.CellPainting> del control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="6b00b-103">You can customize the appearance of any cell by handling the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellPainting> event.</span></span> <span data-ttu-id="6b00b-104">Puede extraer el <xref:System.Drawing.Graphics> del control <xref:System.Windows.Forms.DataGridView> de la propiedad <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> del <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="6b00b-104">You can extract the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Drawing.Graphics> from the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span></span> <span data-ttu-id="6b00b-105">Con esta <xref:System.Drawing.Graphics>, puede afectar a la apariencia del control de <xref:System.Windows.Forms.DataGridView> completo, pero normalmente solo querrá afectar a la apariencia de la celda que se está dibujando actualmente.</span><span class="sxs-lookup"><span data-stu-id="6b00b-105">With this <xref:System.Drawing.Graphics>, you can affect the appearance of the entire <xref:System.Windows.Forms.DataGridView> control, but you will usually want to affect only the appearance of the cell that is currently being painted.</span></span> <span data-ttu-id="6b00b-106">La propiedad <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> del <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> le permite restringir las operaciones de dibujo a la celda que se está dibujando actualmente.</span><span class="sxs-lookup"><span data-stu-id="6b00b-106">The <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> enables you to restrict your painting operations to the cell that is currently being painted.</span></span>  
  
 <span data-ttu-id="6b00b-107">En el ejemplo de código siguiente, dibujará todas las celdas de una `ContactName` columna mediante la combinación de colores del control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="6b00b-107">In the following code example, you will paint all the cells in a `ContactName` column using the <xref:System.Windows.Forms.DataGridView> control's color scheme.</span></span> <span data-ttu-id="6b00b-108">El contenido de texto de cada celda se dibuja en <xref:System.Drawing.Color.Crimson%2A>y un rectángulo de bajorrelieve se dibuja en el mismo color que la propiedad <xref:System.Windows.Forms.DataGridView.GridColor%2A> del control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="6b00b-108">Each cell's text content is painted in <xref:System.Drawing.Color.Crimson%2A>, and an inset rectangle is drawn in the same color as the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b00b-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b00b-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6b00b-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="6b00b-110">Compiling the Code</span></span>  
 <span data-ttu-id="6b00b-111">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="6b00b-111">This example requires:</span></span>  
  
- <span data-ttu-id="6b00b-112">Un control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1` con una columna `ContactName` como la de la tabla Customers de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="6b00b-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a `ContactName` column such as the one in the Customers table in the Northwind sample database.</span></span>  
  
- <span data-ttu-id="6b00b-113">Referencias a los ensamblados System, System.Windows.Forms y System.Drawing.</span><span class="sxs-lookup"><span data-stu-id="6b00b-113">References to the System, System.Windows.Forms, and System.Drawing assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b00b-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6b00b-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [<span data-ttu-id="6b00b-115">Personalizar el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6b00b-115">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
