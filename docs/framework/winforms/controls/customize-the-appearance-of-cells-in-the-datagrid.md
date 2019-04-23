---
title: Procedimiento para personalizar la apariencia de las celdas en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
ms.openlocfilehash: 415cf18aa4cf01b151a414dbc26609af638a7af7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213290"
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="87d3e-102">Procedimiento para personalizar la apariencia de las celdas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="87d3e-102">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="87d3e-103">Puede personalizar la apariencia de cualquier celda controlando el <xref:System.Windows.Forms.DataGridView> del control <xref:System.Windows.Forms.DataGridView.CellPainting> eventos.</span><span class="sxs-lookup"><span data-stu-id="87d3e-103">You can customize the appearance of any cell by handling the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellPainting> event.</span></span> <span data-ttu-id="87d3e-104">Puede extraer el <xref:System.Windows.Forms.DataGridView> del control <xref:System.Drawing.Graphics> desde el <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> propiedad de la <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="87d3e-104">You can extract the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Drawing.Graphics> from the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span></span> <span data-ttu-id="87d3e-105">Con esto <xref:System.Drawing.Graphics>, pueden afectar a la apariencia de todo el <xref:System.Windows.Forms.DataGridView> control, pero normalmente es conveniente afectan únicamente a la apariencia de la celda que se está dibujando actualmente.</span><span class="sxs-lookup"><span data-stu-id="87d3e-105">With this <xref:System.Drawing.Graphics>, you can affect the appearance of the entire <xref:System.Windows.Forms.DataGridView> control, but you will usually want to affect only the appearance of the cell that is currently being painted.</span></span> <span data-ttu-id="87d3e-106">El <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> propiedad de la <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> le permite restringir las operaciones de pintura a la celda que se está dibujando actualmente.</span><span class="sxs-lookup"><span data-stu-id="87d3e-106">The <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> enables you to restrict your painting operations to the cell that is currently being painted.</span></span>  
  
 <span data-ttu-id="87d3e-107">En el ejemplo de código siguiente, se dibujará todas las celdas de un `ContactName` columna mediante el <xref:System.Windows.Forms.DataGridView> combinación de colores del control.</span><span class="sxs-lookup"><span data-stu-id="87d3e-107">In the following code example, you will paint all the cells in a `ContactName` column using the <xref:System.Windows.Forms.DataGridView> control's color scheme.</span></span> <span data-ttu-id="87d3e-108">Contenido de texto de cada celda se pinta en <xref:System.Drawing.Color.Crimson%2A>, y se dibuja un rectángulo de bajorrelieve en el mismo color que el <xref:System.Windows.Forms.DataGridView> del control <xref:System.Windows.Forms.DataGridView.GridColor%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="87d3e-108">Each cell's text content is painted in <xref:System.Drawing.Color.Crimson%2A>, and an inset rectangle is drawn in the same color as the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87d3e-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="87d3e-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="87d3e-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="87d3e-110">Compiling the Code</span></span>  
 <span data-ttu-id="87d3e-111">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="87d3e-111">This example requires:</span></span>  
  
-   <span data-ttu-id="87d3e-112">Un <xref:System.Windows.Forms.DataGridView> control denominado `dataGridView1` con un `ContactName` columna como el de la tabla Customers de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="87d3e-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a `ContactName` column such as the one in the Customers table in the Northwind sample database.</span></span>  
  
-   <span data-ttu-id="87d3e-113">Referencias a los ensamblados System, System.Windows.Forms y System.Drawing.</span><span class="sxs-lookup"><span data-stu-id="87d3e-113">References to the System, System.Windows.Forms, and System.Drawing assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87d3e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="87d3e-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [<span data-ttu-id="87d3e-115">Personalizar el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="87d3e-115">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
