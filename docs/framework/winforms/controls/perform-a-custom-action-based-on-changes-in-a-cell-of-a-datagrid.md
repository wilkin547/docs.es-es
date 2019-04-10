---
title: Filtrar para llevar a cabo una acción personalizada en función de los cambios que se realicen en una celda de un control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], detecting changes
- DataGridView control [Windows Forms], detecting changes in cells
- data grids [Windows Forms], detecting changes in cells
ms.assetid: 7fa44d01-97f4-4ccb-a149-bc72628d2c36
ms.openlocfilehash: 0573199e9afb7e52c7542d36a2f3e39730dacdc4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229165"
---
# <a name="how-to-perform-a-custom-action-based-on-changes-in-a-cell-of-a-windows-forms-datagridview-control"></a><span data-ttu-id="d6db6-102">Filtrar para llevar a cabo una acción personalizada en función de los cambios que se realicen en una celda de un control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d6db6-102">How to: Perform a Custom Action Based on Changes in a Cell of a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="d6db6-103">El <xref:System.Windows.Forms.DataGridView> control tiene un número de eventos que puede usar para detectar cambios en el estado de <xref:System.Windows.Forms.DataGridView> celdas.</span><span class="sxs-lookup"><span data-stu-id="d6db6-103">The <xref:System.Windows.Forms.DataGridView> control has a number of events you can use to detect changes in the state of <xref:System.Windows.Forms.DataGridView> cells.</span></span> <span data-ttu-id="d6db6-104">Dos de los más usados son el <xref:System.Windows.Forms.DataGridView.CellValueChanged> y <xref:System.Windows.Forms.DataGridView.CellStateChanged> eventos.</span><span class="sxs-lookup"><span data-stu-id="d6db6-104">Two of the most commonly used are the <xref:System.Windows.Forms.DataGridView.CellValueChanged> and <xref:System.Windows.Forms.DataGridView.CellStateChanged> events.</span></span>  
  
### <a name="to-detect-changes-in-the-values-of-datagridview-cells"></a><span data-ttu-id="d6db6-105">Para detectar cambios en los valores de las celdas de DataGridView</span><span class="sxs-lookup"><span data-stu-id="d6db6-105">To detect changes in the values of DataGridView cells</span></span>  
  
-   <span data-ttu-id="d6db6-106">Escribir un controlador para el <xref:System.Windows.Forms.DataGridView.CellValueChanged> eventos.</span><span class="sxs-lookup"><span data-stu-id="d6db6-106">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellValueChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#130)]  
  
### <a name="to-detect-changes-in-the-states-of-datagridview-cells"></a><span data-ttu-id="d6db6-107">Para detectar cambios en los Estados de las celdas de DataGridView</span><span class="sxs-lookup"><span data-stu-id="d6db6-107">To detect changes in the states of DataGridView cells</span></span>  
  
-   <span data-ttu-id="d6db6-108">Escribir un controlador para el <xref:System.Windows.Forms.DataGridView.CellStateChanged> eventos.</span><span class="sxs-lookup"><span data-stu-id="d6db6-108">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellStateChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#135)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#135)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d6db6-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="d6db6-109">Compiling the Code</span></span>  
 <span data-ttu-id="d6db6-110">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="d6db6-110">This example requires:</span></span>  
  
-   <span data-ttu-id="d6db6-111">Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="d6db6-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span> <span data-ttu-id="d6db6-112">Para C#, los controladores de eventos deben estar conectados a los eventos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="d6db6-112">For C#, the event handlers must be connected to the corresponding events.</span></span>  
  
-   <span data-ttu-id="d6db6-113">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d6db6-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6db6-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6db6-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellValueChanged?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellStateChanged?displayProperty=nameWithType>
- [<span data-ttu-id="d6db6-115">Programar con celdas, filas y columnas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d6db6-115">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)
- [<span data-ttu-id="d6db6-116">Tutorial: Validar datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d6db6-116">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
