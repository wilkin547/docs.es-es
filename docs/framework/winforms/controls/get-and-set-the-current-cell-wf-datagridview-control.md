---
title: 'Cómo: Obtener y establecer la celda actual en el control DataGridView de formularios Windows Forms'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], getting current cell
- DataGridView control [Windows Forms], setting current cell
- cells [Windows Forms], getting and setting current
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b53d135a1d019ce20dfc8c5c2c1ba59e5968306e
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="a0ac6-102">Cómo: Obtener y establecer la celda actual en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a0ac6-102">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="a0ac6-103">Interacción con el <xref:System.Windows.Forms.DataGridView> a menudo requiere que se descubra mediante programación la celda que está activa actualmente.</span><span class="sxs-lookup"><span data-stu-id="a0ac6-103">Interaction with the <xref:System.Windows.Forms.DataGridView> often requires that you programmatically discover which cell is currently active.</span></span> <span data-ttu-id="a0ac6-104">También debe cambiar la celda actual.</span><span class="sxs-lookup"><span data-stu-id="a0ac6-104">You may also need to change the current cell.</span></span> <span data-ttu-id="a0ac6-105">Puede realizar estas tareas con el <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="a0ac6-105">You can perform these tasks with the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0ac6-106">No se puede establecer la celda actual en una fila o columna que tenga su <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> propiedad establecida en `false`.</span><span class="sxs-lookup"><span data-stu-id="a0ac6-106">You cannot set the current cell in a row or column that has its <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> property set to `false`.</span></span>  
  
 <span data-ttu-id="a0ac6-107">En función de la <xref:System.Windows.Forms.DataGridView> modo de selección del control, si cambia la celda actual puede cambiar la selección.</span><span class="sxs-lookup"><span data-stu-id="a0ac6-107">Depending on the <xref:System.Windows.Forms.DataGridView> control's selection mode, changing the current cell can change the selection.</span></span> <span data-ttu-id="a0ac6-108">Para obtener más información, consulte [modos de selección en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="a0ac6-108">For more information, see [Selection Modes in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-get-the-current-cell-programmatically"></a><span data-ttu-id="a0ac6-109">Para obtener la celda actual mediante programación</span><span class="sxs-lookup"><span data-stu-id="a0ac6-109">To get the current cell programmatically</span></span>  
  
-   <span data-ttu-id="a0ac6-110">Use la <xref:System.Windows.Forms.DataGridView> del control <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="a0ac6-110">Use the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a><span data-ttu-id="a0ac6-111">Para establecer la celda actual mediante programación</span><span class="sxs-lookup"><span data-stu-id="a0ac6-111">To set the current cell programmatically</span></span>  
  
-   <span data-ttu-id="a0ac6-112">Establecer el <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> propiedad de la <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="a0ac6-112">Set the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="a0ac6-113">En el ejemplo de código siguiente, la celda actual se establece en 0, columna 1 de la fila.</span><span class="sxs-lookup"><span data-stu-id="a0ac6-113">In the following code example, the current cell is set to row 0, column 1.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a0ac6-114">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="a0ac6-114">Compiling the Code</span></span>  
 <span data-ttu-id="a0ac6-115">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="a0ac6-115">This example requires:</span></span>  
  
-   <span data-ttu-id="a0ac6-116"><xref:System.Windows.Forms.Button> controles denominados `getCurrentCellButton` y `setCurrentCellButton`.</span><span class="sxs-lookup"><span data-stu-id="a0ac6-116"><xref:System.Windows.Forms.Button> controls named `getCurrentCellButton` and `setCurrentCellButton`.</span></span> <span data-ttu-id="a0ac6-117">En Visual C#, debe asociar el <xref:System.Windows.Forms.Control.Click> eventos para cada botón al controlador de eventos asociados en el código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a0ac6-117">In Visual C#, you must attach the <xref:System.Windows.Forms.Control.Click> events for each button to the associated event handler in the example code.</span></span>  
  
-   <span data-ttu-id="a0ac6-118">Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="a0ac6-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="a0ac6-119">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a0ac6-119">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0ac6-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0ac6-120">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="a0ac6-121">Características básicas de columnas, filas y celdas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a0ac6-121">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 [<span data-ttu-id="a0ac6-122">Modos de selección en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a0ac6-122">Selection Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)
