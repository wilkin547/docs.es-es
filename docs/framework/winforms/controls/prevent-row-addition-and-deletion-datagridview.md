---
title: Impedir la adición y eliminación de filas en el control DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], disabling data entry
- data entry [Windows Forms], disabling in grids
- data grids [Windows Forms], disabling data entry
ms.assetid: ef9539ce-539b-404e-84b6-ac282b64b88c
ms.openlocfilehash: de8e0412faf8c3731f9356771b35a4a5d31b6ec7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728724"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="b7b7e-102">Cómo: Impedir la adición y eliminación de filas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b7b7e-102">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="b7b7e-103">En algunos casos, querrá impedir que los usuarios incluyan nuevas filas de datos o eliminen las filas existentes en el control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-103">Sometimes you will want to prevent users from entering new rows of data or deleting existing rows in your <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="b7b7e-104">La propiedad <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> indica si la fila para nuevos registros está presente en la parte inferior del control, mientras que la propiedad <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> indica si las filas se pueden quitar.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-104">The <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property indicates whether the row for new records is present at the bottom of the control, while the <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> property indicates whether rows can be removed.</span></span> <span data-ttu-id="b7b7e-105">El ejemplo de código siguiente utiliza estas propiedades y también establece la propiedad <xref:System.Windows.Forms.DataGridView.ReadOnly%2A> para que el control sea únicamente de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-105">The following code example uses these properties and also sets the <xref:System.Windows.Forms.DataGridView.ReadOnly%2A> property to make the control entirely read-only.</span></span>  
  
 <span data-ttu-id="b7b7e-106">Visual Studio es compatible con esta tarea.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-106">There is support for this task in Visual Studio.</span></span> <span data-ttu-id="b7b7e-107">Consulte también [Cómo: impedir la adición y eliminación de filas en el control DataGridView Windows Forms mediante el diseñador](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="b7b7e-107">Also see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7b7e-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b7b7e-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#090](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#090)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#090](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#090)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b7b7e-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="b7b7e-109">Compiling the Code</span></span>  
 <span data-ttu-id="b7b7e-110">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="b7b7e-110">This example requires:</span></span>  
  
- <span data-ttu-id="b7b7e-111">Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="b7b7e-112">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b7b7e-112">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7b7e-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b7b7e-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ReadOnly%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A?displayProperty=nameWithType>
- [<span data-ttu-id="b7b7e-114">Características básicas de columnas, filas y celdas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b7b7e-114">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
