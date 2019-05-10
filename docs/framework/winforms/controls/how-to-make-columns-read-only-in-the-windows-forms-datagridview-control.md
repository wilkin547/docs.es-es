---
title: Procedimiento para crear columnas de solo lectura en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], read-only columns
- DataGridView control [Windows Forms], read-only columns
ms.assetid: 2bb73ebb-1a55-4362-9fda-e50574c087d5
ms.openlocfilehash: c865db5caf33b34f12c7acf8078995b12db3c970
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649279"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="f51f9-102">Procedimiento para crear columnas de solo lectura en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f51f9-102">How to: Make Columns Read-Only in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="f51f9-103">No todos los datos están diseñados para ser editados.</span><span class="sxs-lookup"><span data-stu-id="f51f9-103">Not all data is meant for editing.</span></span> <span data-ttu-id="f51f9-104">En el control <xref:System.Windows.Forms.DataGridView>, el valor de propiedad <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> de la columna determina si los usuarios pueden editar las celdas de esa columna.</span><span class="sxs-lookup"><span data-stu-id="f51f9-104">In the <xref:System.Windows.Forms.DataGridView> control, the column <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property value determines whether users can edit cells in that column.</span></span> <span data-ttu-id="f51f9-105">Para obtener información acerca de cómo hacer que el control sea de sólo lectura, vea [Cómo: Impedir la adición de la fila y la eliminación en la Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md).</span><span class="sxs-lookup"><span data-stu-id="f51f9-105">For information about how to make the control entirely read-only, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md).</span></span>  
  
 <span data-ttu-id="f51f9-106">Visual Studio es compatible con esta tarea.</span><span class="sxs-lookup"><span data-stu-id="f51f9-106">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="f51f9-107">Consulte también [Cómo: Crear columnas de sólo lectura en la Windows Forms Control DataGridView de formularios mediante el diseñador](make-columns-read-only-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="f51f9-107">Also see [How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer](make-columns-read-only-in-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-make-a-column-read-only-programmatically"></a><span data-ttu-id="f51f9-108">Para que hacer que una columna sea de solo lectura mediante programación</span><span class="sxs-lookup"><span data-stu-id="f51f9-108">To make a column read-only programmatically</span></span>  
  
- <span data-ttu-id="f51f9-109">Establezca la propiedad <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> en `true`.</span><span class="sxs-lookup"><span data-stu-id="f51f9-109">Set the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#064](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#064)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#064](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#064)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f51f9-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="f51f9-110">Compiling the Code</span></span>  
 <span data-ttu-id="f51f9-111">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="f51f9-111">This example requires:</span></span>  
  
- <span data-ttu-id="f51f9-112">Un control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1` con una columna denominada `CompanyName`.</span><span class="sxs-lookup"><span data-stu-id="f51f9-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a column named `CompanyName`.</span></span>  
  
- <span data-ttu-id="f51f9-113">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f51f9-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f51f9-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f51f9-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f51f9-115">Características básicas de columnas, filas y celdas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f51f9-115">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="f51f9-116">Cómo: Impedir la adición de fila y eliminación en el Control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f51f9-116">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>](prevent-row-addition-and-deletion-datagridview.md)
