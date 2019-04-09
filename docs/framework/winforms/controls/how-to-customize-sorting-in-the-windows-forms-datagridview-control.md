---
title: Filtrar para personalizar la ordenación en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], sorting
- data grids [Windows Forms], customizing sorting
ms.assetid: 92fb5c14-afab-4cf5-a97e-924fd9cb99f5
ms.openlocfilehash: 0e7dffa45dc8d3ac467129d44a7c73a8c4b4bfa2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59192919"
---
# <a name="how-to-customize-sorting-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="f8263-102">Filtrar para personalizar la ordenación en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f8263-102">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="f8263-103">El control <xref:System.Windows.Forms.DataGridView> proporciona ordenación automática pero, dependiendo de sus necesidades, puede que necesite personalizar las operaciones de ordenación.</span><span class="sxs-lookup"><span data-stu-id="f8263-103">The <xref:System.Windows.Forms.DataGridView> control provides automatic sorting but, depending on your needs, you might need to customize sort operations.</span></span> <span data-ttu-id="f8263-104">Por ejemplo, puede usar la ordenación mediante programación para crear una interfaz de usuario alternativa.</span><span class="sxs-lookup"><span data-stu-id="f8263-104">For example, you can use programmatic sorting to create an alternate user interface (UI).</span></span> <span data-ttu-id="f8263-105">También puede controlar el evento <xref:System.Windows.Forms.DataGridView.SortCompare> o llamar a la sobrecarga `Sort(IComparer)` del método <xref:System.Windows.Forms.DataGridView.Sort%2A> para disfrutar de más opciones de ordenación, como la ordenación de varias columnas.</span><span class="sxs-lookup"><span data-stu-id="f8263-105">Alternatively, you can handle the <xref:System.Windows.Forms.DataGridView.SortCompare> event or call the `Sort(IComparer)` overload of the <xref:System.Windows.Forms.DataGridView.Sort%2A> method for greater sorting flexibility, such as sorting multiple columns.</span></span>  
  
 <span data-ttu-id="f8263-106">Los ejemplos de código siguientes muestran estos tres enfoques de la ordenación personalizada.</span><span class="sxs-lookup"><span data-stu-id="f8263-106">The following code examples demonstrate these three approaches to custom sorting.</span></span> <span data-ttu-id="f8263-107">Para más información, consulte [Modos de ordenación de columnas del control DataGridView de Windows Forms](column-sort-modes-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="f8263-107">For more information, see [Column Sort Modes in the Windows Forms DataGridView Control](column-sort-modes-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="programmatic-sorting"></a><span data-ttu-id="f8263-108">Ordenación mediante programación</span><span class="sxs-lookup"><span data-stu-id="f8263-108">Programmatic Sorting</span></span>  
 <span data-ttu-id="f8263-109">En el ejemplo de código siguiente se muestra una ordenación mediante programación usando las propiedades <xref:System.Windows.Forms.DataGridView.SortOrder%2A> y <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> para determinar la dirección de la ordenación, y la propiedad <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A> para establecer manualmente el glifo de ordenación.</span><span class="sxs-lookup"><span data-stu-id="f8263-109">The following code example demonstrates a programmatic sort using the <xref:System.Windows.Forms.DataGridView.SortOrder%2A> and <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> properties to determine the direction of the sort, and the <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A> property to manually set the sort glyph.</span></span> <span data-ttu-id="f8263-110">La sobrecarga `Sort(DataGridViewColumn,ListSortDirection)` del método <xref:System.Windows.Forms.DataGridView.Sort%2A> se usa para ordenar los datos de una sola columna.</span><span class="sxs-lookup"><span data-stu-id="f8263-110">The `Sort(DataGridViewColumn,ListSortDirection)` overload of the <xref:System.Windows.Forms.DataGridView.Sort%2A> method is used to sort data only in a single column.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewProgrammaticSort#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewProgrammaticSort/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewProgrammaticSort#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewProgrammaticSort/VB/form1.vb#00)]  
  
## <a name="custom-sorting-using-the-sortcompare-event"></a><span data-ttu-id="f8263-111">Ordenación personalizada mediante el evento SortCompare</span><span class="sxs-lookup"><span data-stu-id="f8263-111">Custom Sorting Using the SortCompare Event</span></span>  
 <span data-ttu-id="f8263-112">En el ejemplo de código siguiente se muestra la ordenación personalizada mediante un controlador de eventos <xref:System.Windows.Forms.DataGridView.SortCompare>.</span><span class="sxs-lookup"><span data-stu-id="f8263-112">The following code example demonstrates custom sorting using a <xref:System.Windows.Forms.DataGridView.SortCompare> event handler.</span></span> <span data-ttu-id="f8263-113">Se ordena la <xref:System.Windows.Forms.DataGridViewColumn> seleccionada y, si hay valores duplicados en la columna, se usa el identificador de columna para determinar el orden final.</span><span class="sxs-lookup"><span data-stu-id="f8263-113">The selected <xref:System.Windows.Forms.DataGridViewColumn> is sorted and, if there are duplicate values in the column, the ID column is used to determine the final order.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridView.SortCompare#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.SortCompare/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView.SortCompare#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.SortCompare/VB/form1.vb#00)]  
  
## <a name="custom-sorting-using-the-icomparer-interface"></a><span data-ttu-id="f8263-114">Ordenación personalizada mediante la interfaz IComparer</span><span class="sxs-lookup"><span data-stu-id="f8263-114">Custom Sorting Using the IComparer Interface</span></span>  
 <span data-ttu-id="f8263-115">En el ejemplo de código siguiente se muestra la ordenación personalizada mediante la sobrecarga `Sort(IComparer)` del método <xref:System.Windows.Forms.DataGridView.Sort%2A>, que toma una implementación de la interfaz <xref:System.Collections.IComparer> para realizar una ordenación de varias columnas.</span><span class="sxs-lookup"><span data-stu-id="f8263-115">The following code example demonstrates custom sorting using the `Sort(IComparer)` overload of the <xref:System.Windows.Forms.DataGridView.Sort%2A> method, which takes an implementation of the <xref:System.Collections.IComparer> interface to perform a multiple-column sort.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewIComparerSort#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewIComparerSort/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewIComparerSort#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewIComparerSort/VB/form1.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f8263-116">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="f8263-116">Compiling the Code</span></span>  
 <span data-ttu-id="f8263-117">Para estos ejemplos se necesita:</span><span class="sxs-lookup"><span data-stu-id="f8263-117">These examples require:</span></span>  
  
-   <span data-ttu-id="f8263-118">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="f8263-118">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="f8263-119">Para obtener información sobre cómo compilar estos ejemplos desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="f8263-119">For information about building these examples from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="f8263-120">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="f8263-120">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8263-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8263-121">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="f8263-122">Ordenar datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f8263-122">Sorting Data in the Windows Forms DataGridView Control</span></span>](sorting-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f8263-123">Modos de ordenación de columnas del control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f8263-123">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f8263-124">Filtrar para establecer modos de ordenación de columnas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f8263-124">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>](set-the-sort-modes-for-columns-wf-datagridview-control.md)
