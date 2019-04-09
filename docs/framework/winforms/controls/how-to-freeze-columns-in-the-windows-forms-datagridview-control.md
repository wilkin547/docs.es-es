---
title: Filtrar para inmovilizar columnas en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], freezing columns
- DataGridView control [Windows Forms], columns always in view
ms.assetid: 2ef8b1de-782e-4867-af8d-58171ab5c106
ms.openlocfilehash: a0b77a7356b09a5cc95ec165a62c45852f542b8a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187432"
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="0123b-102">Filtrar para inmovilizar columnas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0123b-102">How to: Freeze Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="0123b-103">Cuando los usuarios ven los datos mostrados en un control <xref:System.Windows.Forms.DataGridView> de Windows Forms, a veces deben hacer referencia a una sola columna o a un conjunto de columnas con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="0123b-103">When users view data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, they sometimes need to refer to a single column or set of columns frequently.</span></span> <span data-ttu-id="0123b-104">Por ejemplo, cuando se muestra una tabla de información de clientes que contiene muchas columnas, resulta útil mostrar el nombre del cliente y dejar que otras columnas puedan desplazarse fuera del área visible.</span><span class="sxs-lookup"><span data-stu-id="0123b-104">For example, when displaying a table of customer information that contains many columns, it is useful to display the customer name at all times while enabling other columns to scroll outside the visible region.</span></span>  
  
 <span data-ttu-id="0123b-105">Para conseguir este comportamiento, puede inmovilizar las columnas en el control.</span><span class="sxs-lookup"><span data-stu-id="0123b-105">To achieve this behavior, you can freeze columns in the control.</span></span> <span data-ttu-id="0123b-106">Al inmovilizar una columna, también se inmovilizan todas las columnas situadas a su izquierda (o a su derecha en los scripts de idioma de derecha a izquierda).</span><span class="sxs-lookup"><span data-stu-id="0123b-106">When you freeze a column, all the columns to its left (or to its right in right-to-left language scripts) are frozen as well.</span></span> <span data-ttu-id="0123b-107">Las columnas inmovilizadas permanecen en su lugar mientras que todas las demás columnas se pueden desplazar.</span><span class="sxs-lookup"><span data-stu-id="0123b-107">Frozen columns remain in place while all other columns can scroll.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0123b-108">Si se habilita la reordenación de columnas, las columnas inmovilizadas se tratan como un grupo distinto de las columnas no inmovilizadas.</span><span class="sxs-lookup"><span data-stu-id="0123b-108">If column reordering is enabled, the frozen columns are treated as a group distinct from the unfrozen columns.</span></span> <span data-ttu-id="0123b-109">Los usuarios pueden cambiar la ubicación de las columnas en los grupos, pero no pueden mover una columna de un grupo a otro.</span><span class="sxs-lookup"><span data-stu-id="0123b-109">Users can reposition columns in either group, but they cannot move a column from one group to the other.</span></span>  
  
 <span data-ttu-id="0123b-110">La propiedad <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> de una columna determina si la columna es visible siempre dentro de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="0123b-110">The <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> property of a column determines whether the column is always visible within the grid.</span></span>  
  
 <span data-ttu-id="0123b-111">Visual Studio es compatible con esta tarea.</span><span class="sxs-lookup"><span data-stu-id="0123b-111">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="0123b-112">Consulte también [Cómo: Inmovilizar columnas en el Windows Forms mediante el Diseñador de Control de DataGridView](freeze-columns-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="0123b-112">Also see [How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer](freeze-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-freeze-a-column-programmatically"></a><span data-ttu-id="0123b-113">Para inmovilizar una columna mediante programación</span><span class="sxs-lookup"><span data-stu-id="0123b-113">To freeze a column programmatically</span></span>  
  
-   <span data-ttu-id="0123b-114">Establezca la propiedad <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType> en `true`.</span><span class="sxs-lookup"><span data-stu-id="0123b-114">Set the <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#061](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#061)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#061](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#061)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0123b-115">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="0123b-115">Compiling the Code</span></span>  
 <span data-ttu-id="0123b-116">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="0123b-116">This example requires:</span></span>  
  
-   <span data-ttu-id="0123b-117">Un control <xref:System.Windows.Forms.DataGridView> llamado `dataGridView1` que contiene una columna llamada `AddToCartButton`.</span><span class="sxs-lookup"><span data-stu-id="0123b-117">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `AddToCartButton`.</span></span>  
  
-   <span data-ttu-id="0123b-118">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0123b-118">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0123b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="0123b-119">See also</span></span>

- <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="0123b-120">Características básicas de columnas, filas y celdas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0123b-120">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="0123b-121">Filtrar para habilitar la reordenación de columnas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0123b-121">How to: Enable Column Reordering in the Windows Forms DataGridView Control</span></span>](how-to-enable-column-reordering-in-the-windows-forms-datagridview-control.md)
