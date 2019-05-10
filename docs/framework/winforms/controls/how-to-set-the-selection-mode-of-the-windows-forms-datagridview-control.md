---
title: Procedimiento para establecer el modo de selección del control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
- data grids [Windows Forms], selection mode
ms.assetid: 2f241643-7f82-4583-8757-03494f63b465
ms.openlocfilehash: 22db5c1438405fc830202ec7baac6b6fcd631b41
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64620798"
---
# <a name="how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control"></a><span data-ttu-id="0088c-102">Procedimiento para establecer el modo de selección del control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0088c-102">How to: Set the Selection Mode of the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="0088c-103">En el ejemplo de código siguiente se muestra cómo se configura un <xref:System.Windows.Forms.DataGridView> control para que al hacer clic en cualquier lugar dentro de una fila automáticamente selecciona toda la fila y, por lo que se puede seleccionar que sólo una fila a la vez.</span><span class="sxs-lookup"><span data-stu-id="0088c-103">The following code example demonstrates how to configure a <xref:System.Windows.Forms.DataGridView> control so that clicking anywhere within a row automatically selects the entire row, and so that only one row at a time can be selected.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0088c-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0088c-104">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#065](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#065)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#065](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#065)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0088c-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="0088c-105">Compiling the Code</span></span>  
 <span data-ttu-id="0088c-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="0088c-106">This example requires:</span></span>  
  
- <span data-ttu-id="0088c-107">Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="0088c-107">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="0088c-108">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0088c-108">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0088c-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="0088c-109">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridViewSelectionMode>
- [<span data-ttu-id="0088c-110">Selección y uso del Portapapeles con el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0088c-110">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="0088c-111">Modos de selección en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0088c-111">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)
