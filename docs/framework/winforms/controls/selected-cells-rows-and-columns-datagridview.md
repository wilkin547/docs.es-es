---
title: Obtener las celdas, filas y columnas seleccionadas en el control DataGridView
description: Obtenga información sobre cómo obtener las celdas, filas o columnas seleccionadas desde un control DataGridView usando las propiedades correspondientes.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], DataGridView control [Windows Forms]
- DataGridView control [Windows Forms], getting selection
- getting selection [Windows Forms], DataGridView control [Windows Forms]
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
ms.openlocfilehash: 32ddae34104d23b8e5fbc0cce7da79f33fcce1d2
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904174"
---
# <a name="how-to-get-the-selected-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="c4227-103">Procedimiento para obtener las celdas, filas y columnas seleccionadas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c4227-103">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="c4227-104">Puede obtener las celdas, filas o columnas seleccionadas de un control mediante <xref:System.Windows.Forms.DataGridView> las propiedades correspondientes: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> , <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> y <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> .</span><span class="sxs-lookup"><span data-stu-id="c4227-104">You can get the selected cells, rows, or columns from a <xref:System.Windows.Forms.DataGridView> control by using the corresponding properties: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, and <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span></span> <span data-ttu-id="c4227-105">En los procedimientos siguientes, obtendrá las celdas seleccionadas y mostrará los índices de fila y columna en <xref:System.Windows.Forms.MessageBox> .</span><span class="sxs-lookup"><span data-stu-id="c4227-105">In the following procedures, you will get the selected cells and display their row and column indexes in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
### <a name="to-get-the-selected-cells-in-a-datagridview-control"></a><span data-ttu-id="c4227-106">Para obtener las celdas seleccionadas en un control DataGridView</span><span class="sxs-lookup"><span data-stu-id="c4227-106">To get the selected cells in a DataGridView control</span></span>  
  
- <span data-ttu-id="c4227-107">Utilice la propiedad <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>.</span><span class="sxs-lookup"><span data-stu-id="c4227-107">Use the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> property.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="c4227-108">Use el <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> método para evitar que se muestre un número potencialmente grande de celdas.</span><span class="sxs-lookup"><span data-stu-id="c4227-108">Use the <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> method to avoid showing a potentially large number of cells.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### <a name="to-get-the-selected-rows-in-a-datagridview-control"></a><span data-ttu-id="c4227-109">Para obtener las filas seleccionadas en un control DataGridView</span><span class="sxs-lookup"><span data-stu-id="c4227-109">To get the selected rows in a DataGridView control</span></span>  
  
- <span data-ttu-id="c4227-110">Utilice la propiedad <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>.</span><span class="sxs-lookup"><span data-stu-id="c4227-110">Use the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> property.</span></span> <span data-ttu-id="c4227-111">Para permitir que los usuarios seleccionen filas, debe establecer la <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> propiedad en <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> .</span><span class="sxs-lookup"><span data-stu-id="c4227-111">To enable users to select rows, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### <a name="to-get-the-selected-columns-in-a-datagridview-control"></a><span data-ttu-id="c4227-112">Para obtener las columnas seleccionadas en un control DataGridView</span><span class="sxs-lookup"><span data-stu-id="c4227-112">To get the selected columns in a DataGridView control</span></span>  
  
- <span data-ttu-id="c4227-113">Utilice la propiedad <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span><span class="sxs-lookup"><span data-stu-id="c4227-113">Use the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> property.</span></span> <span data-ttu-id="c4227-114">Para permitir que los usuarios seleccionen columnas, debe establecer la <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> propiedad en <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect> .</span><span class="sxs-lookup"><span data-stu-id="c4227-114">To enable users to select columns, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c4227-115">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="c4227-115">Compiling the Code</span></span>  
 <span data-ttu-id="c4227-116">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="c4227-116">This example requires:</span></span>  
  
- <span data-ttu-id="c4227-117"><xref:System.Windows.Forms.Button>controles denominados `selectedCellsButton` , `selectedRowsButton` y `selectedColumnsButton` , cada uno con controladores para el <xref:System.Windows.Forms.Control.Click> evento asociado.</span><span class="sxs-lookup"><span data-stu-id="c4227-117"><xref:System.Windows.Forms.Button> controls named `selectedCellsButton`, `selectedRowsButton`, and `selectedColumnsButton`, each with handlers for the <xref:System.Windows.Forms.Control.Click> event attached.</span></span>  
  
- <span data-ttu-id="c4227-118">Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="c4227-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="c4227-119">Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> y <xref:System.Text?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c4227-119">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Text?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c4227-120">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="c4227-120">Robust Programming</span></span>  
 <span data-ttu-id="c4227-121">Las colecciones descritas en este tema no funcionan de forma eficaz cuando se selecciona un gran número de celdas, filas o columnas.</span><span class="sxs-lookup"><span data-stu-id="c4227-121">The collections described in this topic do not perform efficiently when large numbers of cells, rows, or columns are selected.</span></span> <span data-ttu-id="c4227-122">Para obtener más información sobre el uso de estas colecciones con grandes cantidades de datos, vea [prácticas recomendadas para escalar el control DataGridView Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="c4227-122">For more information about using these collections with large amounts of data, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4227-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c4227-123">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>
- [<span data-ttu-id="c4227-124">Selección y uso del Portapapeles con el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c4227-124">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
