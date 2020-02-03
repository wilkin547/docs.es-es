---
title: Crear columnas de solo lectura en el control DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], read-only columns
- DataGridView control [Windows Forms], read-only columns
ms.assetid: 2bb73ebb-1a55-4362-9fda-e50574c087d5
ms.openlocfilehash: 11d008d47ec5edb594d3d862c68ff3b9920e0e25
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736187"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="750ff-102">Cómo: Crear columnas de sólo lectura en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="750ff-102">How to: Make Columns Read-Only in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="750ff-103">No todos los datos están diseñados para ser editados.</span><span class="sxs-lookup"><span data-stu-id="750ff-103">Not all data is meant for editing.</span></span> <span data-ttu-id="750ff-104">En el control <xref:System.Windows.Forms.DataGridView>, el valor de propiedad <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> de la columna determina si los usuarios pueden editar las celdas de esa columna.</span><span class="sxs-lookup"><span data-stu-id="750ff-104">In the <xref:System.Windows.Forms.DataGridView> control, the column <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property value determines whether users can edit cells in that column.</span></span> <span data-ttu-id="750ff-105">Para obtener información sobre cómo hacer que el control sea completamente de solo lectura, vea [Cómo: impedir la adición y eliminación de filas en el control DataGridView Windows Forms](prevent-row-addition-and-deletion-datagridview.md).</span><span class="sxs-lookup"><span data-stu-id="750ff-105">For information about how to make the control entirely read-only, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md).</span></span>  
  
 <span data-ttu-id="750ff-106">Visual Studio es compatible con esta tarea.</span><span class="sxs-lookup"><span data-stu-id="750ff-106">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="750ff-107">Consulte también [Cómo: crear columnas de solo lectura en el control DataGridView Windows Forms mediante el diseñador](make-columns-read-only-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="750ff-107">Also see [How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer](make-columns-read-only-in-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-make-a-column-read-only-programmatically"></a><span data-ttu-id="750ff-108">Para que hacer que una columna sea de solo lectura mediante programación</span><span class="sxs-lookup"><span data-stu-id="750ff-108">To make a column read-only programmatically</span></span>  
  
- <span data-ttu-id="750ff-109">Establezca la propiedad <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> en `true`.</span><span class="sxs-lookup"><span data-stu-id="750ff-109">Set the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#064](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#064)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#064](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#064)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="750ff-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="750ff-110">Compiling the Code</span></span>  
 <span data-ttu-id="750ff-111">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="750ff-111">This example requires:</span></span>  
  
- <span data-ttu-id="750ff-112">Un control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1` con una columna denominada `CompanyName`.</span><span class="sxs-lookup"><span data-stu-id="750ff-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a column named `CompanyName`.</span></span>  
  
- <span data-ttu-id="750ff-113">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="750ff-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="750ff-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="750ff-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="750ff-115">Características básicas de columnas, filas y celdas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="750ff-115">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="750ff-116">Impedir la adición y eliminación de filas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="750ff-116">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>](prevent-row-addition-and-deletion-datagridview.md)
