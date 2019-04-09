---
title: Filtrar para habilitar la reordenación de columnas en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- data grids [Windows Forms], reordering columns
- columns [Windows Forms], reordering
ms.assetid: cc20eae3-e4db-493f-95ce-a4215e29472a
ms.openlocfilehash: 625c4987a45ed3749284e7abc7b6cde6d24821ca
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59161478"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="34cd2-102">Filtrar para habilitar la reordenación de columnas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="34cd2-102">How to: Enable Column Reordering in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="34cd2-103">Al habilitar la reordenación de columnas en el control <xref:System.Windows.Forms.DataGridView>, los usuarios pueden mover una columna a una nueva posición arrastrando el encabezado de la columna con el mouse.</span><span class="sxs-lookup"><span data-stu-id="34cd2-103">When you enable column reordering in the <xref:System.Windows.Forms.DataGridView> control, users can move a column to a new position by dragging the column header with the mouse.</span></span> <span data-ttu-id="34cd2-104">En el control <xref:System.Windows.Forms.DataGridView>, el valor de la propiedad <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> determina si los usuarios pueden mover las columnas a otras posiciones.</span><span class="sxs-lookup"><span data-stu-id="34cd2-104">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> property value determines whether users can move columns to different positions.</span></span>  
  
 <span data-ttu-id="34cd2-105">Visual Studio es compatible con esta tarea.</span><span class="sxs-lookup"><span data-stu-id="34cd2-105">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="34cd2-106">Consulte también [Cómo: Habilitar reordenación de columnas en la Windows Forms mediante el Diseñador de Control de DataGridView](enable-column-reordering-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="34cd2-106">Also see [How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer](enable-column-reordering-in-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-enable-column-reordering-programmatically"></a><span data-ttu-id="34cd2-107">Para habilitar mediante programación la reordenación de columnas</span><span class="sxs-lookup"><span data-stu-id="34cd2-107">To enable column reordering programmatically</span></span>  
  
-   <span data-ttu-id="34cd2-108">Establezca la propiedad <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> en `true`.</span><span class="sxs-lookup"><span data-stu-id="34cd2-108">Set the <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#060](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#060)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#060](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#060)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="34cd2-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="34cd2-109">Compiling the Code</span></span>  
 <span data-ttu-id="34cd2-110">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="34cd2-110">This example requires:</span></span>  
  
-   <span data-ttu-id="34cd2-111">Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="34cd2-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="34cd2-112">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="34cd2-112">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34cd2-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="34cd2-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [<span data-ttu-id="34cd2-114">Características básicas de columnas, filas y celdas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="34cd2-114">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="34cd2-115">Filtrar para inmovilizar columnas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="34cd2-115">How to: Freeze Columns in the Windows Forms DataGridView Control</span></span>](how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)
