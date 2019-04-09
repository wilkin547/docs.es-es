---
title: Filtrar para establecer modos de ordenación de columnas en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], data grids
- DataGridView control [Windows Forms], sort mode
- data grids [Windows Forms], sorting data
ms.assetid: 57dfed60-a608-40d5-86f9-d65686ffb325
ms.openlocfilehash: 4894de00a323f70ca244ea877101a5af1cbb37e0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096373"
---
# <a name="how-to-set-the-sort-modes-for-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="8d54a-102">Filtrar para establecer modos de ordenación de columnas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8d54a-102">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="8d54a-103">En el <xref:System.Windows.Forms.DataGridView> las columnas del cuadro de texto de control, utilizan la clasificación automática de forma predeterminada, mientras que otros tipos de columna no se ordenan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8d54a-103">In the <xref:System.Windows.Forms.DataGridView> control, text box columns use automatic sorting by default, while other column types are not sorted automatically.</span></span> <span data-ttu-id="8d54a-104">A veces desea invalidar estos valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="8d54a-104">Sometimes you will want to override these defaults.</span></span> <span data-ttu-id="8d54a-105">Por ejemplo, puede mostrar imágenes en lugar de texto, números o valores de celda de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="8d54a-105">For example, you can display images in place of text, numbers, or enumeration cell values.</span></span> <span data-ttu-id="8d54a-106">Mientras no se pueden ordenar las imágenes, se pueden ordenar los valores subyacentes que representan.</span><span class="sxs-lookup"><span data-stu-id="8d54a-106">While the images cannot be sorted, the underlying values that they represent can be sorted.</span></span>  
  
 <span data-ttu-id="8d54a-107">En el <xref:System.Windows.Forms.DataGridView> (control), el <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> valor de propiedad de una columna determina su comportamiento de ordenación.</span><span class="sxs-lookup"><span data-stu-id="8d54a-107">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property value of a column determines its sorting behavior.</span></span>  
  
 <span data-ttu-id="8d54a-108">El procedimiento siguiente se muestra el `Priority` columna desde [Cómo: Personalizar el formato de datos en el Control DataGridView de Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="8d54a-108">The following procedure shows the `Priority` column from [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span> <span data-ttu-id="8d54a-109">Esta columna es una columna de imagen y no se puede ordenar de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8d54a-109">This column is an image column and is not sortable by default.</span></span> <span data-ttu-id="8d54a-110">Contiene valores de celda reales que son cadenas, sin embargo, por lo que pueden ordenarse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8d54a-110">It contains actual cell values that are strings, however, so it can be sorted automatically.</span></span>  
  
### <a name="to-set-the-sort-mode-for-a-column"></a><span data-ttu-id="8d54a-111">Para establecer el modo de ordenación para una columna</span><span class="sxs-lookup"><span data-stu-id="8d54a-111">To set the sort mode for a column</span></span>  
  
-   <span data-ttu-id="8d54a-112">Establecer la propiedad <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8d54a-112">Set the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#066](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#066)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#066](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#066)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8d54a-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="8d54a-113">Compiling the Code</span></span>  
 <span data-ttu-id="8d54a-114">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="8d54a-114">This example requires:</span></span>  
  
-   <span data-ttu-id="8d54a-115">Un control <xref:System.Windows.Forms.DataGridView> llamado `dataGridView1` que contiene una columna llamada `Priority`.</span><span class="sxs-lookup"><span data-stu-id="8d54a-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `Priority`.</span></span>  
  
-   <span data-ttu-id="8d54a-116">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8d54a-116">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d54a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d54a-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="8d54a-118">Ordenar datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8d54a-118">Sorting Data in the Windows Forms DataGridView Control</span></span>](sorting-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="8d54a-119">Modos de ordenación de columnas del control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8d54a-119">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="8d54a-120">Filtrar para personalizar la ordenación en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8d54a-120">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
