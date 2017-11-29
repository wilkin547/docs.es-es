---
title: "Cómo: Personalizar la apariencia de las celdas en el control DataGridView de formularios Windows Forms"
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
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 545a3bff5e810f9c0a995366e7f6460930f9e936
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="671b6-102">Cómo: Personalizar la apariencia de las celdas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="671b6-102">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="671b6-103">Puede personalizar la apariencia de cualquier celda controlando el <xref:System.Windows.Forms.DataGridView> del control <xref:System.Windows.Forms.DataGridView.CellPainting> eventos.</span><span class="sxs-lookup"><span data-stu-id="671b6-103">You can customize the appearance of any cell by handling the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellPainting> event.</span></span> <span data-ttu-id="671b6-104">Puede extraer el <xref:System.Windows.Forms.DataGridView> del control <xref:System.Drawing.Graphics> desde el <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> propiedad de la <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="671b6-104">You can extract the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Drawing.Graphics> from the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span></span> <span data-ttu-id="671b6-105">Con esto <xref:System.Drawing.Graphics>, pueden afectar a la apariencia de todo el <xref:System.Windows.Forms.DataGridView> control, pero normalmente es conveniente afectan únicamente a la apariencia de la celda que se está dibujando actualmente.</span><span class="sxs-lookup"><span data-stu-id="671b6-105">With this <xref:System.Drawing.Graphics>, you can affect the appearance of the entire <xref:System.Windows.Forms.DataGridView> control, but you will usually want to affect only the appearance of the cell that is currently being painted.</span></span> <span data-ttu-id="671b6-106">El <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> propiedad de la <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> le permite restringir las operaciones de dibujo a la celda que se está dibujando actualmente.</span><span class="sxs-lookup"><span data-stu-id="671b6-106">The <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> enables you to restrict your painting operations to the cell that is currently being painted.</span></span>  
  
 <span data-ttu-id="671b6-107">En el ejemplo de código siguiente, se dibujará todas las celdas en una `ContactName` de columna con el <xref:System.Windows.Forms.DataGridView> combinación de colores del control.</span><span class="sxs-lookup"><span data-stu-id="671b6-107">In the following code example, you will paint all the cells in a `ContactName` column using the <xref:System.Windows.Forms.DataGridView> control's color scheme.</span></span> <span data-ttu-id="671b6-108">El contenido de texto de cada celda se pinta en <xref:System.Drawing.Color.Crimson%2A>, y se dibuja un rectángulo de bajorrelieve en el mismo color que el <xref:System.Windows.Forms.DataGridView> del control <xref:System.Windows.Forms.DataGridView.GridColor%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="671b6-108">Each cell's text content is painted in <xref:System.Drawing.Color.Crimson%2A>, and an inset rectangle is drawn in the same color as the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="671b6-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="671b6-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="671b6-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="671b6-110">Compiling the Code</span></span>  
 <span data-ttu-id="671b6-111">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="671b6-111">This example requires:</span></span>  
  
-   <span data-ttu-id="671b6-112">A <xref:System.Windows.Forms.DataGridView> control denominado `dataGridView1` con un `ContactName` columna como la de la tabla Customers de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="671b6-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a `ContactName` column such as the one in the Customers table in the Northwind sample database.</span></span>  
  
-   <span data-ttu-id="671b6-113">Referencias a los ensamblados System, System.Windows.Forms y System.Drawing.</span><span class="sxs-lookup"><span data-stu-id="671b6-113">References to the System, System.Windows.Forms, and System.Drawing assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="671b6-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="671b6-114">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.CellPainting>  
 [<span data-ttu-id="671b6-115">Personalizar el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="671b6-115">Customizing the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)
