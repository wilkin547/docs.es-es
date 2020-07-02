---
title: Obtener y establecer la celda actual en el control DataGridView
description: Obtenga información sobre cómo detectar mediante programación qué celda está activa actualmente obteniendo y estableciendo la celda actual en el control DataGridView Windows Forms.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], getting current cell
- DataGridView control [Windows Forms], setting current cell
- cells [Windows Forms], getting and setting current
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
ms.openlocfilehash: 1651ca9c8fa0329f9435a70ce777bce68f15ff63
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622216"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="86adf-103">Procedimiento para obtener y establecer la celda actual en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="86adf-103">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="86adf-104">La interacción con <xref:System.Windows.Forms.DataGridView> suele requerir que se detecte mediante programación qué celda está activa actualmente.</span><span class="sxs-lookup"><span data-stu-id="86adf-104">Interaction with the <xref:System.Windows.Forms.DataGridView> often requires that you programmatically discover which cell is currently active.</span></span> <span data-ttu-id="86adf-105">También puede que necesite cambiar la celda actual.</span><span class="sxs-lookup"><span data-stu-id="86adf-105">You may also need to change the current cell.</span></span> <span data-ttu-id="86adf-106">Puede realizar estas tareas con la <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="86adf-106">You can perform these tasks with the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="86adf-107">No se puede establecer la celda actual en una fila o columna que tenga su <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> propiedad establecida en `false` .</span><span class="sxs-lookup"><span data-stu-id="86adf-107">You cannot set the current cell in a row or column that has its <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> property set to `false`.</span></span>  
  
 <span data-ttu-id="86adf-108">Dependiendo del modo de <xref:System.Windows.Forms.DataGridView> selección del control, cambiar la celda actual puede cambiar la selección.</span><span class="sxs-lookup"><span data-stu-id="86adf-108">Depending on the <xref:System.Windows.Forms.DataGridView> control's selection mode, changing the current cell can change the selection.</span></span> <span data-ttu-id="86adf-109">Para obtener más información, vea [modos de selección en el control DataGridView Windows Forms](selection-modes-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="86adf-109">For more information, see [Selection Modes in the Windows Forms DataGridView Control](selection-modes-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-get-the-current-cell-programmatically"></a><span data-ttu-id="86adf-110">Para obtener la celda actual mediante programación</span><span class="sxs-lookup"><span data-stu-id="86adf-110">To get the current cell programmatically</span></span>  
  
- <span data-ttu-id="86adf-111">Use la <xref:System.Windows.Forms.DataGridView> propiedad del control <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> .</span><span class="sxs-lookup"><span data-stu-id="86adf-111">Use the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a><span data-ttu-id="86adf-112">Para establecer la celda actual mediante programación</span><span class="sxs-lookup"><span data-stu-id="86adf-112">To set the current cell programmatically</span></span>  
  
- <span data-ttu-id="86adf-113">Establezca la <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> propiedad del <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="86adf-113">Set the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="86adf-114">En el ejemplo de código siguiente, la celda actual se establece en la fila 0, columna 1.</span><span class="sxs-lookup"><span data-stu-id="86adf-114">In the following code example, the current cell is set to row 0, column 1.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="86adf-115">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="86adf-115">Compiling the Code</span></span>  
 <span data-ttu-id="86adf-116">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="86adf-116">This example requires:</span></span>  
  
- <span data-ttu-id="86adf-117"><xref:System.Windows.Forms.Button>controles denominados `getCurrentCellButton` y `setCurrentCellButton` .</span><span class="sxs-lookup"><span data-stu-id="86adf-117"><xref:System.Windows.Forms.Button> controls named `getCurrentCellButton` and `setCurrentCellButton`.</span></span> <span data-ttu-id="86adf-118">En Visual C#, debe adjuntar los <xref:System.Windows.Forms.Control.Click> eventos de cada botón al controlador de eventos asociado en el código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="86adf-118">In Visual C#, you must attach the <xref:System.Windows.Forms.Control.Click> events for each button to the associated event handler in the example code.</span></span>  
  
- <span data-ttu-id="86adf-119">Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="86adf-119">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="86adf-120">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="86adf-120">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86adf-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="86adf-121">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [<span data-ttu-id="86adf-122">Características básicas de columnas, filas y celdas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="86adf-122">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="86adf-123">Modos de selección en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="86adf-123">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)
