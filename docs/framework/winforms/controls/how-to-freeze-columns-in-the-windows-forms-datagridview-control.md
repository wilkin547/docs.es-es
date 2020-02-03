---
title: Inmovilizar columnas en el control DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], freezing columns
- DataGridView control [Windows Forms], columns always in view
ms.assetid: 2ef8b1de-782e-4867-af8d-58171ab5c106
ms.openlocfilehash: 6d1a98e5c4332078c6012cb7c9ed836108abd86c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736750"
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="83ebf-102">Cómo: Inmovilizar columnas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="83ebf-102">How to: Freeze Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="83ebf-103">Cuando los usuarios ven los datos mostrados en un control <xref:System.Windows.Forms.DataGridView> de Windows Forms, a veces deben hacer referencia a una sola columna o a un conjunto de columnas con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="83ebf-103">When users view data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, they sometimes need to refer to a single column or set of columns frequently.</span></span> <span data-ttu-id="83ebf-104">Por ejemplo, cuando se muestra una tabla de información de clientes que contiene muchas columnas, resulta útil mostrar el nombre del cliente y dejar que otras columnas puedan desplazarse fuera del área visible.</span><span class="sxs-lookup"><span data-stu-id="83ebf-104">For example, when displaying a table of customer information that contains many columns, it is useful to display the customer name at all times while enabling other columns to scroll outside the visible region.</span></span>  
  
 <span data-ttu-id="83ebf-105">Para conseguir este comportamiento, puede inmovilizar las columnas en el control.</span><span class="sxs-lookup"><span data-stu-id="83ebf-105">To achieve this behavior, you can freeze columns in the control.</span></span> <span data-ttu-id="83ebf-106">Al inmovilizar una columna, también se inmovilizan todas las columnas situadas a su izquierda (o a su derecha en los scripts de idioma de derecha a izquierda).</span><span class="sxs-lookup"><span data-stu-id="83ebf-106">When you freeze a column, all the columns to its left (or to its right in right-to-left language scripts) are frozen as well.</span></span> <span data-ttu-id="83ebf-107">Las columnas inmovilizadas permanecen en su lugar mientras que todas las demás columnas se pueden desplazar.</span><span class="sxs-lookup"><span data-stu-id="83ebf-107">Frozen columns remain in place while all other columns can scroll.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="83ebf-108">Si se habilita la reordenación de columnas, las columnas inmovilizadas se tratan como un grupo distinto de las columnas no inmovilizadas.</span><span class="sxs-lookup"><span data-stu-id="83ebf-108">If column reordering is enabled, the frozen columns are treated as a group distinct from the unfrozen columns.</span></span> <span data-ttu-id="83ebf-109">Los usuarios pueden cambiar la ubicación de las columnas en los grupos, pero no pueden mover una columna de un grupo a otro.</span><span class="sxs-lookup"><span data-stu-id="83ebf-109">Users can reposition columns in either group, but they cannot move a column from one group to the other.</span></span>  
  
 <span data-ttu-id="83ebf-110">La propiedad <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> de una columna determina si la columna es visible siempre dentro de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="83ebf-110">The <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> property of a column determines whether the column is always visible within the grid.</span></span>  
  
 <span data-ttu-id="83ebf-111">Visual Studio es compatible con esta tarea.</span><span class="sxs-lookup"><span data-stu-id="83ebf-111">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="83ebf-112">Consulte también [Cómo: inmovilizar columnas en el control DataGridView Windows Forms mediante el diseñador](freeze-columns-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="83ebf-112">Also see [How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer](freeze-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-freeze-a-column-programmatically"></a><span data-ttu-id="83ebf-113">Para inmovilizar una columna mediante programación</span><span class="sxs-lookup"><span data-stu-id="83ebf-113">To freeze a column programmatically</span></span>  
  
- <span data-ttu-id="83ebf-114">Establezca la propiedad <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType> en `true`.</span><span class="sxs-lookup"><span data-stu-id="83ebf-114">Set the <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#061](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#061)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#061](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#061)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="83ebf-115">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="83ebf-115">Compiling the Code</span></span>  
 <span data-ttu-id="83ebf-116">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="83ebf-116">This example requires:</span></span>  
  
- <span data-ttu-id="83ebf-117">Un control <xref:System.Windows.Forms.DataGridView> llamado `dataGridView1` que contiene una columna llamada `AddToCartButton`.</span><span class="sxs-lookup"><span data-stu-id="83ebf-117">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `AddToCartButton`.</span></span>  
  
- <span data-ttu-id="83ebf-118">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="83ebf-118">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83ebf-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="83ebf-119">See also</span></span>

- <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="83ebf-120">Características básicas de columnas, filas y celdas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="83ebf-120">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="83ebf-121">Habilitar la reordenación de columnas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="83ebf-121">How to: Enable Column Reordering in the Windows Forms DataGridView Control</span></span>](how-to-enable-column-reordering-in-the-windows-forms-datagridview-control.md)
