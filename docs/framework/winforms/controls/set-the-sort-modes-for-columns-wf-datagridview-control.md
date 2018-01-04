---
title: "Cómo: Establecer modos de ordenación de columnas en el control DataGridView de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], data grids
- DataGridView control [Windows Forms], sort mode
- data grids [Windows Forms], sorting data
ms.assetid: 57dfed60-a608-40d5-86f9-d65686ffb325
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6a8571209ea0a80a64c1f30336c9a52b1bc79622
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-sort-modes-for-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="08d25-102">Cómo: Establecer modos de ordenación de columnas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="08d25-102">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="08d25-103">En el <xref:System.Windows.Forms.DataGridView> columnas del cuadro de texto de control, use la clasificación automática de forma predeterminada, mientras que otros tipos de columna no se ordenan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="08d25-103">In the <xref:System.Windows.Forms.DataGridView> control, text box columns use automatic sorting by default, while other column types are not sorted automatically.</span></span> <span data-ttu-id="08d25-104">En ocasiones, deseará invalidar estos valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="08d25-104">Sometimes you will want to override these defaults.</span></span> <span data-ttu-id="08d25-105">Por ejemplo, puede mostrar imágenes en lugar de texto, números o valores de celda de enumeración.</span><span class="sxs-lookup"><span data-stu-id="08d25-105">For example, you can display images in place of text, numbers, or enumeration cell values.</span></span> <span data-ttu-id="08d25-106">Mientras no se pueden ordenar las imágenes, se pueden ordenar los valores subyacentes que representan.</span><span class="sxs-lookup"><span data-stu-id="08d25-106">While the images cannot be sorted, the underlying values that they represent can be sorted.</span></span>  
  
 <span data-ttu-id="08d25-107">En el <xref:System.Windows.Forms.DataGridView> (control), el <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> valor de la propiedad de una columna determina su comportamiento de ordenación.</span><span class="sxs-lookup"><span data-stu-id="08d25-107">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property value of a column determines its sorting behavior.</span></span>  
  
 <span data-ttu-id="08d25-108">El siguiente procedimiento se muestra la `Priority` columna de [Cómo: personalizar el formato de datos en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="08d25-108">The following procedure shows the `Priority` column from [How to: Customize Data Formatting in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span> <span data-ttu-id="08d25-109">Esta columna es una columna de imagen y no se puede ordenar de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="08d25-109">This column is an image column and is not sortable by default.</span></span> <span data-ttu-id="08d25-110">Contiene valores de celda reales que son cadenas, sin embargo, por lo que se puede ordenar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="08d25-110">It contains actual cell values that are strings, however, so it can be sorted automatically.</span></span>  
  
### <a name="to-set-the-sort-mode-for-a-column"></a><span data-ttu-id="08d25-111">Para establecer el modo de ordenación para una columna</span><span class="sxs-lookup"><span data-stu-id="08d25-111">To set the sort mode for a column</span></span>  
  
-   <span data-ttu-id="08d25-112">Establecer la propiedad <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="08d25-112">Set the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#066](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#066)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#066](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#066)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="08d25-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="08d25-113">Compiling the Code</span></span>  
 <span data-ttu-id="08d25-114">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="08d25-114">This example requires:</span></span>  
  
-   <span data-ttu-id="08d25-115">Un control <xref:System.Windows.Forms.DataGridView> llamado `dataGridView1` que contiene una columna llamada `Priority`.</span><span class="sxs-lookup"><span data-stu-id="08d25-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `Priority`.</span></span>  
  
-   <span data-ttu-id="08d25-116">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="08d25-116">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08d25-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="08d25-117">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="08d25-118">Ordenar datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="08d25-118">Sorting Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="08d25-119">Modos de ordenación de columnas del control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="08d25-119">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="08d25-120">Personalizar la ordenación en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="08d25-120">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
