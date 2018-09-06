---
title: 'Cómo: Crear columnas de sólo lectura en el control DataGridView de formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], read-only columns
- DataGridView control [Windows Forms], read-only columns
ms.assetid: 2bb73ebb-1a55-4362-9fda-e50574c087d5
ms.openlocfilehash: a8b5c0f9492941cf0e01e016d9fb097e1df44d2e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43731980"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="2c478-102">Cómo: Crear columnas de sólo lectura en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2c478-102">How to: Make Columns Read-Only in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2c478-103">No todos los datos están diseñados para ser editados.</span><span class="sxs-lookup"><span data-stu-id="2c478-103">Not all data is meant for editing.</span></span> <span data-ttu-id="2c478-104">En el control <xref:System.Windows.Forms.DataGridView>, el valor de propiedad <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> de la columna determina si los usuarios pueden editar las celdas de esa columna.</span><span class="sxs-lookup"><span data-stu-id="2c478-104">In the <xref:System.Windows.Forms.DataGridView> control, the column <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property value determines whether users can edit cells in that column.</span></span> <span data-ttu-id="2c478-105">Para obtener información acerca de cómo hacer que el control sea de sólo lectura, vea [Cómo: impedir la adición de fila y la eliminación en el DataGridView Control de formularios de Windows](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md).</span><span class="sxs-lookup"><span data-stu-id="2c478-105">For information about how to make the control entirely read-only, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md).</span></span>  
  
 <span data-ttu-id="2c478-106">Visual Studio es compatible con esta tarea.</span><span class="sxs-lookup"><span data-stu-id="2c478-106">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="2c478-107">Consulte también [Cómo: asegúrese de solo lectura de las columnas en la Windows Forms DataGridView Control mediante el diseñador](https://msdn.microsoft.com/library/xd4k3c7e\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="2c478-107">Also see [How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer](https://msdn.microsoft.com/library/xd4k3c7e\(v=vs.110\)).</span></span>  
  
### <a name="to-make-a-column-read-only-programmatically"></a><span data-ttu-id="2c478-108">Para que hacer que una columna sea de solo lectura mediante programación</span><span class="sxs-lookup"><span data-stu-id="2c478-108">To make a column read-only programmatically</span></span>  
  
-   <span data-ttu-id="2c478-109">Establezca la propiedad <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> en `true`.</span><span class="sxs-lookup"><span data-stu-id="2c478-109">Set the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#064](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#064)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#064](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#064)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2c478-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="2c478-110">Compiling the Code</span></span>  
 <span data-ttu-id="2c478-111">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="2c478-111">This example requires:</span></span>  
  
-   <span data-ttu-id="2c478-112">Un control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1` con una columna denominada `CompanyName`.</span><span class="sxs-lookup"><span data-stu-id="2c478-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a column named `CompanyName`.</span></span>  
  
-   <span data-ttu-id="2c478-113">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2c478-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c478-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c478-114">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="2c478-115">Características básicas de columnas, filas y celdas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2c478-115">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 [<span data-ttu-id="2c478-116">Impedir la adición y eliminación de filas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2c478-116">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md)
