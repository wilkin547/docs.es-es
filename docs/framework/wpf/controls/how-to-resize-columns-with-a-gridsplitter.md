---
title: "Cómo: Cambiar el tamaño de columnas con un GridSplitter"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- grid columns [WPF], resizing
- GridSplitter control [WPF], resizing grid columns
- resizing grid columns [WPF]
ms.assetid: 47b20fe6-7adc-4aa6-9693-b4e184eef74b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d68d829e5543b1c299668493c11b62ccb11d81af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-resize-columns-with-a-gridsplitter"></a><span data-ttu-id="28d76-102">Cómo: Cambiar el tamaño de columnas con un GridSplitter</span><span class="sxs-lookup"><span data-stu-id="28d76-102">How to: Resize Columns with a GridSplitter</span></span>
<span data-ttu-id="28d76-103">Este ejemplo muestra cómo crear una vertical <xref:System.Windows.Controls.GridSplitter> para redistribuir el espacio entre las dos columnas de una <xref:System.Windows.Controls.Grid> sin cambiar las dimensiones de la <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="28d76-103">This example shows how to create a vertical <xref:System.Windows.Controls.GridSplitter> in order to redistribute the space between two columns in a <xref:System.Windows.Controls.Grid> without changing the dimensions of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28d76-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="28d76-104">Example</span></span>  
 <span data-ttu-id="28d76-105">**Cómo crear un control GridSplitter que se superponga al borde de una columna**</span><span class="sxs-lookup"><span data-stu-id="28d76-105">**How to create a GridSplitter that overlays the edge of a column**</span></span>  
  
 <span data-ttu-id="28d76-106">Para especificar un <xref:System.Windows.Controls.GridSplitter> que cambia el tamaño de las columnas adyacentes en un <xref:System.Windows.Controls.Grid>, establezca el <xref:System.Windows.Controls.Grid.Column%2A> propiedad adjunta a una de las columnas que desee cambiar.</span><span class="sxs-lookup"><span data-stu-id="28d76-106">To specify a <xref:System.Windows.Controls.GridSplitter> that resizes adjacent columns in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Column%2A> attached property to one of the columns that you want to resize.</span></span> <span data-ttu-id="28d76-107">Si su <xref:System.Windows.Controls.Grid> tiene más de una fila, establezca el <xref:System.Windows.Controls.Grid.RowSpan%2A> propiedad adjunta en el número de filas.</span><span class="sxs-lookup"><span data-stu-id="28d76-107">If your <xref:System.Windows.Controls.Grid> has more than one row, set the <xref:System.Windows.Controls.Grid.RowSpan%2A> attached property to the number of rows.</span></span> <span data-ttu-id="28d76-108">A continuación, establezca el <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> propiedad <xref:System.Windows.HorizontalAlignment.Left> o <xref:System.Windows.HorizontalAlignment.Right> (la alineación establezca dependerá en las dos columnas que desea cambiar el tamaño).</span><span class="sxs-lookup"><span data-stu-id="28d76-108">Then set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property to <xref:System.Windows.HorizontalAlignment.Left> or <xref:System.Windows.HorizontalAlignment.Right> (which alignment you set depends on which two columns you want to resize).</span></span> <span data-ttu-id="28d76-109">Por último, establezca el <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> propiedad <xref:System.Windows.VerticalAlignment.Stretch>.</span><span class="sxs-lookup"><span data-stu-id="28d76-109">Finally, set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> property to <xref:System.Windows.VerticalAlignment.Stretch>.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterColumnOverlay](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplittercolumnoverlay)]  
  
 <span data-ttu-id="28d76-110">A <xref:System.Windows.Controls.GridSplitter> que no tiene su propia columna pueden estar ocultos por otros controles en la <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="28d76-110">A <xref:System.Windows.Controls.GridSplitter> that does not have its own column may be obscured by other controls in the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="28d76-111">Para más información sobre cómo evitar este problema, vea [Asegurarse de que un GridSplitter es visible](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).</span><span class="sxs-lookup"><span data-stu-id="28d76-111">For more information about how to prevent this issue, see [Make Sure That a GridSplitter Is Visible](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).</span></span>  
  
 <span data-ttu-id="28d76-112">**Cómo crear un control GridSplitter que ocupa una columna**</span><span class="sxs-lookup"><span data-stu-id="28d76-112">**How to create a GridSplitter that occupies a column**</span></span>  
  
 <span data-ttu-id="28d76-113">Para especificar un <xref:System.Windows.Controls.GridSplitter> que ocupa una columna en una <xref:System.Windows.Controls.Grid>, establezca el <xref:System.Windows.Controls.Grid.Column%2A> propiedad adjunta a una de las columnas que desee cambiar.</span><span class="sxs-lookup"><span data-stu-id="28d76-113">To specify a <xref:System.Windows.Controls.GridSplitter> that occupies a column in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Column%2A> attached property to one of the columns that you want to resize.</span></span> <span data-ttu-id="28d76-114">Si la cuadrícula tiene más de una fila, establezca el <xref:System.Windows.Controls.Grid.RowSpan%2A> propiedad adjunta en el número de filas.</span><span class="sxs-lookup"><span data-stu-id="28d76-114">If your Grid has more than one row, set the <xref:System.Windows.Controls.Grid.RowSpan%2A> attached property to the number of rows.</span></span> <span data-ttu-id="28d76-115">A continuación, establezca el <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> a <xref:System.Windows.HorizontalAlignment.Center>, establezca el <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> propiedad a <xref:System.Windows.VerticalAlignment.Stretch>y establezca el <xref:System.Windows.Controls.ColumnDefinition.Width%2A> de la columna que contiene el <xref:System.Windows.Controls.GridSplitter> a <xref:System.Windows.GridLength.Auto%2A>.</span><span class="sxs-lookup"><span data-stu-id="28d76-115">Then set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> to <xref:System.Windows.HorizontalAlignment.Center>, set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> property to <xref:System.Windows.VerticalAlignment.Stretch>, and set the <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of the column that contains the <xref:System.Windows.Controls.GridSplitter> to <xref:System.Windows.GridLength.Auto%2A>.</span></span>  
  
 <span data-ttu-id="28d76-116">En el ejemplo siguiente se muestra cómo definir una vertical <xref:System.Windows.Controls.GridSplitter> que ocupa una columna y cambia el tamaño de las columnas en cada lado del mismo.</span><span class="sxs-lookup"><span data-stu-id="28d76-116">The following example shows how to define a vertical <xref:System.Windows.Controls.GridSplitter> that occupies a column and resizes the columns on either side of it.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart2)]  
  
## <a name="see-also"></a><span data-ttu-id="28d76-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="28d76-117">See Also</span></span>  
 <xref:System.Windows.Controls.GridSplitter>  
 [<span data-ttu-id="28d76-118">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="28d76-118">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)
