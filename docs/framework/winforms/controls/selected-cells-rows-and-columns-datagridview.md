---
title: Procedimiento Obtener las celdas seleccionadas, filas y columnas en el Control DataGridView de formularios de Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], DataGridView control [Windows Forms]
- DataGridView control [Windows Forms], getting selection
- getting selection [Windows Forms], DataGridView control [Windows Forms]
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
ms.openlocfilehash: 95229f1915b25962a700a7d6aced0a012bbe6657
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54626919"
---
# <a name="how-to-get-the-selected-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="a2d90-102">Procedimiento Obtener las celdas seleccionadas, filas y columnas en el Control DataGridView de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="a2d90-102">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="a2d90-103">Puede obtener las celdas seleccionadas, filas o columnas de una <xref:System.Windows.Forms.DataGridView> control mediante el uso de las propiedades correspondientes: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, y <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span><span class="sxs-lookup"><span data-stu-id="a2d90-103">You can get the selected cells, rows, or columns from a <xref:System.Windows.Forms.DataGridView> control by using the corresponding properties: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, and <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span></span> <span data-ttu-id="a2d90-104">En los procedimientos siguientes, obtendrá las celdas seleccionadas y mostrar sus índices de fila y columna en un <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="a2d90-104">In the following procedures, you will get the selected cells and display their row and column indexes in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
### <a name="to-get-the-selected-cells-in-a-datagridview-control"></a><span data-ttu-id="a2d90-105">Para obtener las celdas seleccionadas en un control DataGridView</span><span class="sxs-lookup"><span data-stu-id="a2d90-105">To get the selected cells in a DataGridView control</span></span>  
  
-   <span data-ttu-id="a2d90-106">Utilice la propiedad <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>.</span><span class="sxs-lookup"><span data-stu-id="a2d90-106">Use the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> property.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a2d90-107">Use el <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> método para evitar que aparezca un número potencialmente grande de celdas.</span><span class="sxs-lookup"><span data-stu-id="a2d90-107">Use the <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> method to avoid showing a potentially large number of cells.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### <a name="to-get-the-selected-rows-in-a-datagridview-control"></a><span data-ttu-id="a2d90-108">Para obtener las filas seleccionadas en un control DataGridView</span><span class="sxs-lookup"><span data-stu-id="a2d90-108">To get the selected rows in a DataGridView control</span></span>  
  
-   <span data-ttu-id="a2d90-109">Utilice la propiedad <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>.</span><span class="sxs-lookup"><span data-stu-id="a2d90-109">Use the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> property.</span></span> <span data-ttu-id="a2d90-110">Para permitir que los usuarios seleccionar las filas, debe establecer el <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> propiedad <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.</span><span class="sxs-lookup"><span data-stu-id="a2d90-110">To enable users to select rows, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### <a name="to-get-the-selected-columns-in-a-datagridview-control"></a><span data-ttu-id="a2d90-111">Para obtener las columnas seleccionadas en un control DataGridView</span><span class="sxs-lookup"><span data-stu-id="a2d90-111">To get the selected columns in a DataGridView control</span></span>  
  
-   <span data-ttu-id="a2d90-112">Utilice la propiedad <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span><span class="sxs-lookup"><span data-stu-id="a2d90-112">Use the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> property.</span></span> <span data-ttu-id="a2d90-113">Para habilitar a los usuarios seleccionar las columnas, debe establecer el <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> propiedad <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.</span><span class="sxs-lookup"><span data-stu-id="a2d90-113">To enable users to select columns, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a2d90-114">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="a2d90-114">Compiling the Code</span></span>  
 <span data-ttu-id="a2d90-115">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="a2d90-115">This example requires:</span></span>  
  
-   <span data-ttu-id="a2d90-116"><xref:System.Windows.Forms.Button> controles denominados `selectedCellsButton`, `selectedRowsButton`, y `selectedColumnsButton`, cada uno con controladores para el <xref:System.Windows.Forms.Control.Click> evento adjunto.</span><span class="sxs-lookup"><span data-stu-id="a2d90-116"><xref:System.Windows.Forms.Button> controls named `selectedCellsButton`, `selectedRowsButton`, and `selectedColumnsButton`, each with handlers for the <xref:System.Windows.Forms.Control.Click> event attached.</span></span>  
  
-   <span data-ttu-id="a2d90-117">Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="a2d90-117">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="a2d90-118">Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> y <xref:System.Text?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a2d90-118">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Text?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a2d90-119">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="a2d90-119">Robust Programming</span></span>  
 <span data-ttu-id="a2d90-120">Las colecciones que se describe en este tema no realizan eficazmente cuando se selecciona el gran número de celdas, filas o columnas.</span><span class="sxs-lookup"><span data-stu-id="a2d90-120">The collections described in this topic do not perform efficiently when large numbers of cells, rows, or columns are selected.</span></span> <span data-ttu-id="a2d90-121">Para obtener más información sobre el uso de estas colecciones con grandes cantidades de datos, vea [mejores prácticas para escalar el DataGridView Control de Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="a2d90-121">For more information about using these collections with large amounts of data, see [Best Practices for Scaling the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2d90-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2d90-122">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>
- [<span data-ttu-id="a2d90-123">Selección y uso del Portapapeles con el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a2d90-123">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
