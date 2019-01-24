---
title: Procedimiento Obtener y establecer la celda actual en el Control DataGridView de formularios de Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], getting current cell
- DataGridView control [Windows Forms], setting current cell
- cells [Windows Forms], getting and setting current
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
ms.openlocfilehash: 2508551cd4bcb056d1e746b2dc962c4500093ea5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54495609"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="50422-102">Procedimiento Obtener y establecer la celda actual en el Control DataGridView de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="50422-102">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="50422-103">Interacción con el <xref:System.Windows.Forms.DataGridView> a menudo requiere que detectar mediante programación la celda que está actualmente activa.</span><span class="sxs-lookup"><span data-stu-id="50422-103">Interaction with the <xref:System.Windows.Forms.DataGridView> often requires that you programmatically discover which cell is currently active.</span></span> <span data-ttu-id="50422-104">También es posible que deba cambiar la celda actual.</span><span class="sxs-lookup"><span data-stu-id="50422-104">You may also need to change the current cell.</span></span> <span data-ttu-id="50422-105">Puede realizar estas tareas con el <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="50422-105">You can perform these tasks with the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50422-106">No se puede establecer la celda actual en una fila o columna que tiene su <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> propiedad establecida en `false`.</span><span class="sxs-lookup"><span data-stu-id="50422-106">You cannot set the current cell in a row or column that has its <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> property set to `false`.</span></span>  
  
 <span data-ttu-id="50422-107">En función de la <xref:System.Windows.Forms.DataGridView> modo de selección del control, cambiar la celda actual puede cambiar la selección.</span><span class="sxs-lookup"><span data-stu-id="50422-107">Depending on the <xref:System.Windows.Forms.DataGridView> control's selection mode, changing the current cell can change the selection.</span></span> <span data-ttu-id="50422-108">Para obtener más información, consulte [modos de selección en el DataGridView Control de Windows Forms](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="50422-108">For more information, see [Selection Modes in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-get-the-current-cell-programmatically"></a><span data-ttu-id="50422-109">Para obtener la celda actual mediante programación</span><span class="sxs-lookup"><span data-stu-id="50422-109">To get the current cell programmatically</span></span>  
  
-   <span data-ttu-id="50422-110">Use la <xref:System.Windows.Forms.DataGridView> del control <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="50422-110">Use the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a><span data-ttu-id="50422-111">Para establecer la celda actual mediante programación</span><span class="sxs-lookup"><span data-stu-id="50422-111">To set the current cell programmatically</span></span>  
  
-   <span data-ttu-id="50422-112">Establecer el <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> propiedad de la <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="50422-112">Set the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="50422-113">En el ejemplo de código siguiente, se establece la celda actual en la fila 0, columna 1.</span><span class="sxs-lookup"><span data-stu-id="50422-113">In the following code example, the current cell is set to row 0, column 1.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="50422-114">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="50422-114">Compiling the Code</span></span>  
 <span data-ttu-id="50422-115">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="50422-115">This example requires:</span></span>  
  
-   <span data-ttu-id="50422-116"><xref:System.Windows.Forms.Button> controles denominados `getCurrentCellButton` y `setCurrentCellButton`.</span><span class="sxs-lookup"><span data-stu-id="50422-116"><xref:System.Windows.Forms.Button> controls named `getCurrentCellButton` and `setCurrentCellButton`.</span></span> <span data-ttu-id="50422-117">En Visual C#, debe asociar el <xref:System.Windows.Forms.Control.Click> eventos para cada botón al controlador de eventos asociados en el código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="50422-117">In Visual C#, you must attach the <xref:System.Windows.Forms.Control.Click> events for each button to the associated event handler in the example code.</span></span>  
  
-   <span data-ttu-id="50422-118">Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="50422-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="50422-119">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="50422-119">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50422-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="50422-120">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [<span data-ttu-id="50422-121">Características básicas de columnas, filas y celdas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="50422-121">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="50422-122">Modos de selección en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="50422-122">Selection Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)
