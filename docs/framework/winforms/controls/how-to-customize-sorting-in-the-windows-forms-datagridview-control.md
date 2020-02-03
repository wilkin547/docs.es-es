---
title: Personalizar la ordenación en un control DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], sorting
- data grids [Windows Forms], customizing sorting
ms.assetid: 92fb5c14-afab-4cf5-a97e-924fd9cb99f5
ms.openlocfilehash: 20f581b2df6fd172a0a1998aed60c56b0306f2eb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743179"
---
# <a name="how-to-customize-sorting-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="86075-102">Cómo: Personalizar la ordenación en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="86075-102">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="86075-103">El control <xref:System.Windows.Forms.DataGridView> proporciona ordenación automática pero, dependiendo de sus necesidades, puede que necesite personalizar las operaciones de ordenación.</span><span class="sxs-lookup"><span data-stu-id="86075-103">The <xref:System.Windows.Forms.DataGridView> control provides automatic sorting but, depending on your needs, you might need to customize sort operations.</span></span> <span data-ttu-id="86075-104">Por ejemplo, puede usar la ordenación mediante programación para crear una interfaz de usuario alternativa.</span><span class="sxs-lookup"><span data-stu-id="86075-104">For example, you can use programmatic sorting to create an alternate user interface (UI).</span></span> <span data-ttu-id="86075-105">También puede controlar el evento <xref:System.Windows.Forms.DataGridView.SortCompare> o llamar a la sobrecarga `Sort(IComparer)` del método <xref:System.Windows.Forms.DataGridView.Sort%2A> para disfrutar de más opciones de ordenación, como la ordenación de varias columnas.</span><span class="sxs-lookup"><span data-stu-id="86075-105">Alternatively, you can handle the <xref:System.Windows.Forms.DataGridView.SortCompare> event or call the `Sort(IComparer)` overload of the <xref:System.Windows.Forms.DataGridView.Sort%2A> method for greater sorting flexibility, such as sorting multiple columns.</span></span>  
  
 <span data-ttu-id="86075-106">Los ejemplos de código siguientes muestran estos tres enfoques de la ordenación personalizada.</span><span class="sxs-lookup"><span data-stu-id="86075-106">The following code examples demonstrate these three approaches to custom sorting.</span></span> <span data-ttu-id="86075-107">Para más información, consulte [Modos de ordenación de columnas del control DataGridView de Windows Forms](column-sort-modes-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="86075-107">For more information, see [Column Sort Modes in the Windows Forms DataGridView Control](column-sort-modes-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="programmatic-sorting"></a><span data-ttu-id="86075-108">Ordenación mediante programación</span><span class="sxs-lookup"><span data-stu-id="86075-108">Programmatic Sorting</span></span>  
 <span data-ttu-id="86075-109">En el ejemplo de código siguiente se muestra una ordenación mediante programación usando las propiedades <xref:System.Windows.Forms.DataGridView.SortOrder%2A> y <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> para determinar la dirección de la ordenación, y la propiedad <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A> para establecer manualmente el glifo de ordenación.</span><span class="sxs-lookup"><span data-stu-id="86075-109">The following code example demonstrates a programmatic sort using the <xref:System.Windows.Forms.DataGridView.SortOrder%2A> and <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> properties to determine the direction of the sort, and the <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A> property to manually set the sort glyph.</span></span> <span data-ttu-id="86075-110">La sobrecarga `Sort(DataGridViewColumn,ListSortDirection)` del método <xref:System.Windows.Forms.DataGridView.Sort%2A> se usa para ordenar los datos de una sola columna.</span><span class="sxs-lookup"><span data-stu-id="86075-110">The `Sort(DataGridViewColumn,ListSortDirection)` overload of the <xref:System.Windows.Forms.DataGridView.Sort%2A> method is used to sort data only in a single column.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewProgrammaticSort#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewProgrammaticSort/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewProgrammaticSort#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewProgrammaticSort/VB/form1.vb#00)]  
  
## <a name="custom-sorting-using-the-sortcompare-event"></a><span data-ttu-id="86075-111">Ordenación personalizada mediante el evento SortCompare</span><span class="sxs-lookup"><span data-stu-id="86075-111">Custom Sorting Using the SortCompare Event</span></span>  
 <span data-ttu-id="86075-112">En el ejemplo de código siguiente se muestra la ordenación personalizada mediante un controlador de eventos <xref:System.Windows.Forms.DataGridView.SortCompare>.</span><span class="sxs-lookup"><span data-stu-id="86075-112">The following code example demonstrates custom sorting using a <xref:System.Windows.Forms.DataGridView.SortCompare> event handler.</span></span> <span data-ttu-id="86075-113">Se ordena la <xref:System.Windows.Forms.DataGridViewColumn> seleccionada y, si hay valores duplicados en la columna, se usa el identificador de columna para determinar el orden final.</span><span class="sxs-lookup"><span data-stu-id="86075-113">The selected <xref:System.Windows.Forms.DataGridViewColumn> is sorted and, if there are duplicate values in the column, the ID column is used to determine the final order.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridView.SortCompare#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.SortCompare/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView.SortCompare#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.SortCompare/VB/form1.vb#00)]  
  
## <a name="custom-sorting-using-the-icomparer-interface"></a><span data-ttu-id="86075-114">Ordenación personalizada mediante la interfaz IComparer</span><span class="sxs-lookup"><span data-stu-id="86075-114">Custom Sorting Using the IComparer Interface</span></span>  
 <span data-ttu-id="86075-115">En el ejemplo de código siguiente se muestra la ordenación personalizada mediante la sobrecarga `Sort(IComparer)` del método <xref:System.Windows.Forms.DataGridView.Sort%2A>, que toma una implementación de la interfaz <xref:System.Collections.IComparer> para realizar una ordenación de varias columnas.</span><span class="sxs-lookup"><span data-stu-id="86075-115">The following code example demonstrates custom sorting using the `Sort(IComparer)` overload of the <xref:System.Windows.Forms.DataGridView.Sort%2A> method, which takes an implementation of the <xref:System.Collections.IComparer> interface to perform a multiple-column sort.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewIComparerSort#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewIComparerSort/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewIComparerSort#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewIComparerSort/VB/form1.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="86075-116">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="86075-116">Compiling the Code</span></span>  
 <span data-ttu-id="86075-117">Estos ejemplos requieren:</span><span class="sxs-lookup"><span data-stu-id="86075-117">These examples require:</span></span>  
  
- <span data-ttu-id="86075-118">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="86075-118">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86075-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="86075-119">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="86075-120">Ordenar datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="86075-120">Sorting Data in the Windows Forms DataGridView Control</span></span>](sorting-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="86075-121">Modos de ordenación de columnas del control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="86075-121">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="86075-122">Cómo: Establecer modos de ordenación de columnas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="86075-122">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>](set-the-sort-modes-for-columns-wf-datagridview-control.md)
