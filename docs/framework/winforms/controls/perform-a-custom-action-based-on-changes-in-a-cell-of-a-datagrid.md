---
title: Realizar una acción personalizada basada en cambios en la celda del control DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], detecting changes
- DataGridView control [Windows Forms], detecting changes in cells
- data grids [Windows Forms], detecting changes in cells
ms.assetid: 7fa44d01-97f4-4ccb-a149-bc72628d2c36
ms.openlocfilehash: a809134b0a79bc9685c5b84acce58b4c61b5c526
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744280"
---
# <a name="how-to-perform-a-custom-action-based-on-changes-in-a-cell-of-a-windows-forms-datagridview-control"></a><span data-ttu-id="397b3-102">Cómo: Llevar a cabo una acción personalizada en función de los cambios que se realicen en una celda de un control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="397b3-102">How to: Perform a Custom Action Based on Changes in a Cell of a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="397b3-103">El control <xref:System.Windows.Forms.DataGridView> tiene varios eventos que se pueden utilizar para detectar cambios en el estado de <xref:System.Windows.Forms.DataGridView> celdas.</span><span class="sxs-lookup"><span data-stu-id="397b3-103">The <xref:System.Windows.Forms.DataGridView> control has a number of events you can use to detect changes in the state of <xref:System.Windows.Forms.DataGridView> cells.</span></span> <span data-ttu-id="397b3-104">Dos de las más utilizadas son los eventos <xref:System.Windows.Forms.DataGridView.CellValueChanged> y <xref:System.Windows.Forms.DataGridView.CellStateChanged>.</span><span class="sxs-lookup"><span data-stu-id="397b3-104">Two of the most commonly used are the <xref:System.Windows.Forms.DataGridView.CellValueChanged> and <xref:System.Windows.Forms.DataGridView.CellStateChanged> events.</span></span>  
  
### <a name="to-detect-changes-in-the-values-of-datagridview-cells"></a><span data-ttu-id="397b3-105">Para detectar cambios en los valores de las celdas de DataGridView</span><span class="sxs-lookup"><span data-stu-id="397b3-105">To detect changes in the values of DataGridView cells</span></span>  
  
- <span data-ttu-id="397b3-106">Escriba un controlador para el evento <xref:System.Windows.Forms.DataGridView.CellValueChanged>.</span><span class="sxs-lookup"><span data-stu-id="397b3-106">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellValueChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#130)]  
  
### <a name="to-detect-changes-in-the-states-of-datagridview-cells"></a><span data-ttu-id="397b3-107">Para detectar cambios en los Estados de las celdas de DataGridView</span><span class="sxs-lookup"><span data-stu-id="397b3-107">To detect changes in the states of DataGridView cells</span></span>  
  
- <span data-ttu-id="397b3-108">Escriba un controlador para el evento <xref:System.Windows.Forms.DataGridView.CellStateChanged>.</span><span class="sxs-lookup"><span data-stu-id="397b3-108">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellStateChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#135)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#135)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="397b3-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="397b3-109">Compiling the Code</span></span>  
 <span data-ttu-id="397b3-110">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="397b3-110">This example requires:</span></span>  
  
- <span data-ttu-id="397b3-111">Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="397b3-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span> <span data-ttu-id="397b3-112">Para C#, los controladores de eventos deben estar conectados a los eventos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="397b3-112">For C#, the event handlers must be connected to the corresponding events.</span></span>  
  
- <span data-ttu-id="397b3-113">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="397b3-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="397b3-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="397b3-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellValueChanged?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellStateChanged?displayProperty=nameWithType>
- [<span data-ttu-id="397b3-115">Programar con celdas, filas y columnas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="397b3-115">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)
- [<span data-ttu-id="397b3-116">Tutorial: Validar datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="397b3-116">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
