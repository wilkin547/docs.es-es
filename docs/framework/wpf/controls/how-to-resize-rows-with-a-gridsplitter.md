---
title: "Cómo: Cambiar el tamaño de filas con un GridSplitter"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- resizing grid rows [WPF]
- grid rows [WPF], resizing
- GridSplitter control [WPF], resizing grid rows
ms.assetid: 2413a9f2-1d81-46ed-95cb-95ec8233eea2
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2d4cf06a86a1da7bb34074623f8f19f4bda7a724
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-resize-rows-with-a-gridsplitter"></a><span data-ttu-id="602a1-102">Cómo: Cambiar el tamaño de filas con un GridSplitter</span><span class="sxs-lookup"><span data-stu-id="602a1-102">How to: Resize Rows with a GridSplitter</span></span>
<span data-ttu-id="602a1-103">Este ejemplo muestra cómo utilizar una horizontal <xref:System.Windows.Controls.GridSplitter> para redistribuir el espacio entre las dos filas de un <xref:System.Windows.Controls.Grid> sin cambiar las dimensiones de la <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="602a1-103">This example shows how to use a horizontal <xref:System.Windows.Controls.GridSplitter> to redistribute the space between two rows in a <xref:System.Windows.Controls.Grid> without changing the dimensions of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="602a1-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="602a1-104">Example</span></span>  
 <span data-ttu-id="602a1-105">**Cómo crear un control GridSplitter que se superponga al borde de una fila**</span><span class="sxs-lookup"><span data-stu-id="602a1-105">**How to create a GridSplitter that overlays the edge of a row**</span></span>  
  
 <span data-ttu-id="602a1-106">Para especificar un <xref:System.Windows.Controls.GridSplitter> que cambia el tamaño de filas adyacentes en un <xref:System.Windows.Controls.Grid>, establezca el <xref:System.Windows.Controls.Grid.Row%2A> propiedad adjunta a una de las filas que desee cambiar.</span><span class="sxs-lookup"><span data-stu-id="602a1-106">To specify a <xref:System.Windows.Controls.GridSplitter> that resizes adjacent rows in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Row%2A> attached property to one of the rows that you want to resize.</span></span> <span data-ttu-id="602a1-107">Si su <xref:System.Windows.Controls.Grid> tiene más de una columna, establezca la <xref:System.Windows.Controls.Grid.ColumnSpan%2A> propiedad adjunta para especificar el número de columnas.</span><span class="sxs-lookup"><span data-stu-id="602a1-107">If your <xref:System.Windows.Controls.Grid> has more than one column, set the <xref:System.Windows.Controls.Grid.ColumnSpan%2A> attached property to specify the number of columns.</span></span> <span data-ttu-id="602a1-108">A continuación, establezca el <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> a <xref:System.Windows.VerticalAlignment.Top> o <xref:System.Windows.VerticalAlignment.Bottom> (la alineación que establezca depende en que dos filas que desea cambiar el tamaño).</span><span class="sxs-lookup"><span data-stu-id="602a1-108">Then set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> to <xref:System.Windows.VerticalAlignment.Top> or <xref:System.Windows.VerticalAlignment.Bottom> (which alignment you set depends on which two rows you want to resize).</span></span> <span data-ttu-id="602a1-109">Por último, establezca el <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> propiedad <xref:System.Windows.HorizontalAlignment.Stretch>.</span><span class="sxs-lookup"><span data-stu-id="602a1-109">Finally, set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property to <xref:System.Windows.HorizontalAlignment.Stretch>.</span></span>  
  
 <span data-ttu-id="602a1-110">En el ejemplo siguiente se muestra cómo definir una horizontal <xref:System.Windows.Controls.GridSplitter> que cambia el tamaño de las filas adyacentes.</span><span class="sxs-lookup"><span data-stu-id="602a1-110">The following example shows how to define a horizontal <xref:System.Windows.Controls.GridSplitter> that resizes adjacent rows.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterRowOverlay](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterrowoverlay)]  
  
 <span data-ttu-id="602a1-111">A <xref:System.Windows.Controls.GridSplitter> que no ocupe su propia fila pueden estar ocultos por otros controles en la <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="602a1-111">A <xref:System.Windows.Controls.GridSplitter> that does not occupy its own row may be obscured by other controls in the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="602a1-112">Para más información sobre cómo evitar este problema, vea [Asegurarse de que un GridSplitter es visible](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).</span><span class="sxs-lookup"><span data-stu-id="602a1-112">For more information about how to prevent this issue, see [Make Sure That a GridSplitter Is Visible](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).</span></span>  
  
 <span data-ttu-id="602a1-113">**Cómo crear un control GridSplitter que ocupa una fila**</span><span class="sxs-lookup"><span data-stu-id="602a1-113">**How to create a GridSplitter that occupies a row**</span></span>  
  
 <span data-ttu-id="602a1-114">Para especificar un <xref:System.Windows.Controls.GridSplitter> que ocupa una fila en un <xref:System.Windows.Controls.Grid>, establezca el <xref:System.Windows.Controls.Grid.Row%2A> propiedad adjunta a una de las filas que desee cambiar.</span><span class="sxs-lookup"><span data-stu-id="602a1-114">To specify a <xref:System.Windows.Controls.GridSplitter> that occupies a row in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Row%2A> attached property to one of the rows that you want to resize.</span></span> <span data-ttu-id="602a1-115">Si su <xref:System.Windows.Controls.Grid> tiene más de una columna, establezca la <xref:System.Windows.Controls.Grid.ColumnSpan%2A> propiedad adjunta en el número de columnas.</span><span class="sxs-lookup"><span data-stu-id="602a1-115">If your <xref:System.Windows.Controls.Grid> has more than one column, set the <xref:System.Windows.Controls.Grid.ColumnSpan%2A> attached property to the number of columns.</span></span> <span data-ttu-id="602a1-116">A continuación, establezca el <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> a <xref:System.Windows.VerticalAlignment.Center>, establezca el <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> propiedad a <xref:System.Windows.HorizontalAlignment.Stretch>y establezca el <xref:System.Windows.Controls.RowDefinition.Height%2A> de la fila que contiene el <xref:System.Windows.Controls.GridSplitter> a <xref:System.Windows.GridLength.Auto%2A>.</span><span class="sxs-lookup"><span data-stu-id="602a1-116">Then set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> to <xref:System.Windows.VerticalAlignment.Center>, set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property to <xref:System.Windows.HorizontalAlignment.Stretch>, and set the <xref:System.Windows.Controls.RowDefinition.Height%2A> of the row that contains the <xref:System.Windows.Controls.GridSplitter> to <xref:System.Windows.GridLength.Auto%2A>.</span></span>  
  
 <span data-ttu-id="602a1-117">En el ejemplo siguiente se muestra cómo definir una horizontal <xref:System.Windows.Controls.GridSplitter> que ocupa una fila y cambia el tamaño de las filas en ambos lados de él.</span><span class="sxs-lookup"><span data-stu-id="602a1-117">The following example shows how to define a horizontal <xref:System.Windows.Controls.GridSplitter> that occupies a row and resizes the rows on either side of it.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart2)]  
  
## <a name="see-also"></a><span data-ttu-id="602a1-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="602a1-118">See Also</span></span>  
 <xref:System.Windows.Controls.GridSplitter>  
 [<span data-ttu-id="602a1-119">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="602a1-119">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)
