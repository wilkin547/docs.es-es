---
title: Procedimiento Habilitar la reordenación de columnas en el Control DataGridView de Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- data grids [Windows Forms], reordering columns
- columns [Windows Forms], reordering
ms.assetid: cc20eae3-e4db-493f-95ce-a4215e29472a
ms.openlocfilehash: e216a91a612c5d4370d5786492426f757f39a262
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658096"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="70a2b-102">Procedimiento Habilitar la reordenación de columnas en el Control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="70a2b-102">How to: Enable Column Reordering in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="70a2b-103">Al habilitar la reordenación de columnas en el control <xref:System.Windows.Forms.DataGridView>, los usuarios pueden mover una columna a una nueva posición arrastrando el encabezado de la columna con el mouse.</span><span class="sxs-lookup"><span data-stu-id="70a2b-103">When you enable column reordering in the <xref:System.Windows.Forms.DataGridView> control, users can move a column to a new position by dragging the column header with the mouse.</span></span> <span data-ttu-id="70a2b-104">En el control <xref:System.Windows.Forms.DataGridView>, el valor de la propiedad <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> determina si los usuarios pueden mover las columnas a otras posiciones.</span><span class="sxs-lookup"><span data-stu-id="70a2b-104">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> property value determines whether users can move columns to different positions.</span></span>  
  
 <span data-ttu-id="70a2b-105">Visual Studio es compatible con esta tarea.</span><span class="sxs-lookup"><span data-stu-id="70a2b-105">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="70a2b-106">Consulte también [Cómo: Habilitar la reordenación de columnas en el Control de DataGridView de Windows Forms mediante el diseñador](https://msdn.microsoft.com/library/8xwtyc86\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="70a2b-106">Also see [How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer](https://msdn.microsoft.com/library/8xwtyc86\(v=vs.110\))</span></span>  
  
### <a name="to-enable-column-reordering-programmatically"></a><span data-ttu-id="70a2b-107">Para habilitar mediante programación la reordenación de columnas</span><span class="sxs-lookup"><span data-stu-id="70a2b-107">To enable column reordering programmatically</span></span>  
  
-   <span data-ttu-id="70a2b-108">Establezca la propiedad <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> en `true`.</span><span class="sxs-lookup"><span data-stu-id="70a2b-108">Set the <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#060](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#060)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#060](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#060)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="70a2b-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="70a2b-109">Compiling the Code</span></span>  
 <span data-ttu-id="70a2b-110">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="70a2b-110">This example requires:</span></span>  
  
-   <span data-ttu-id="70a2b-111">Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="70a2b-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="70a2b-112">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="70a2b-112">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70a2b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="70a2b-113">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [<span data-ttu-id="70a2b-114">Características básicas de columnas, filas y celdas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="70a2b-114">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="70a2b-115">Cómo: Inmovilizar columnas en el Control DataGridView de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="70a2b-115">How to: Freeze Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)
