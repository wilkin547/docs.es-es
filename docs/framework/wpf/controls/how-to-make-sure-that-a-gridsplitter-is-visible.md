---
title: Procedimiento Asegurarse de que un GridSplitter es visible
ms.date: 03/30/2017
helpviewer_keywords:
- GridSplitter control [WPF], ensuring visibility of
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
ms.openlocfilehash: b7543d14ba39d854b5a2c3f4d0d19b9a457ea89b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59147152"
---
# <a name="how-to-make-sure-that-a-gridsplitter-is-visible"></a><span data-ttu-id="25e49-102">Procedimiento Asegurarse de que un GridSplitter es visible</span><span class="sxs-lookup"><span data-stu-id="25e49-102">How to: Make Sure That a GridSplitter Is Visible</span></span>
<span data-ttu-id="25e49-103">En este ejemplo se muestra cómo asegurarse de que un <xref:System.Windows.Controls.GridSplitter> control no está oculto por los otros controles en un <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="25e49-103">This example shows how to make sure a <xref:System.Windows.Controls.GridSplitter> control is not hidden by the other controls in a <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25e49-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="25e49-104">Example</span></span>  
 <span data-ttu-id="25e49-105">El <xref:System.Windows.Controls.Panel.Children%2A> de un <xref:System.Windows.Controls.Grid> control se representan en el orden en que se definen en el marcado o código.</span><span class="sxs-lookup"><span data-stu-id="25e49-105">The <xref:System.Windows.Controls.Panel.Children%2A> of a <xref:System.Windows.Controls.Grid> control are rendered in the order that they are defined in markup or code.</span></span> <span data-ttu-id="25e49-106"><xref:System.Windows.Controls.GridSplitter> se pueden ocultar los controles por otros controles si no se define como los últimos elementos en el <xref:System.Windows.Controls.Panel.Children%2A> colección o si proporcionan otros controles de una mayor <xref:System.Windows.Controls.Panel.ZIndexProperty>.</span><span class="sxs-lookup"><span data-stu-id="25e49-106"><xref:System.Windows.Controls.GridSplitter> controls can be hidden by other controls if you do not define them as the last elements in the <xref:System.Windows.Controls.Panel.Children%2A> collection or if you give other controls a higher <xref:System.Windows.Controls.Panel.ZIndexProperty>.</span></span>  
  
 <span data-ttu-id="25e49-107">Para evitar que oculta <xref:System.Windows.Controls.GridSplitter> controles, realice una de las siguientes acciones.</span><span class="sxs-lookup"><span data-stu-id="25e49-107">To prevent hidden <xref:System.Windows.Controls.GridSplitter> controls, do one of the following.</span></span>  
  
-   <span data-ttu-id="25e49-108">Asegúrese de que <xref:System.Windows.Controls.GridSplitter> controles son las últimas <xref:System.Windows.Controls.Panel.Children%2A> agregado a la <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="25e49-108">Make sure that <xref:System.Windows.Controls.GridSplitter> controls are the last <xref:System.Windows.Controls.Panel.Children%2A> added to the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="25e49-109">El ejemplo siguiente se muestra el <xref:System.Windows.Controls.GridSplitter> como el último elemento en el <xref:System.Windows.Controls.Panel.Children%2A> colección de la <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="25e49-109">The following example shows the <xref:System.Windows.Controls.GridSplitter> as the last element in the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterLastChild](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
-   <span data-ttu-id="25e49-110">Establecer el <xref:System.Windows.Controls.Panel.ZIndexProperty> en el <xref:System.Windows.Controls.GridSplitter> encima de un control que podría ocultarlo.</span><span class="sxs-lookup"><span data-stu-id="25e49-110">Set the <xref:System.Windows.Controls.Panel.ZIndexProperty> on the <xref:System.Windows.Controls.GridSplitter> to be higher than a control that would otherwise hide it.</span></span> <span data-ttu-id="25e49-111">El siguiente ejemplo se da el <xref:System.Windows.Controls.GridSplitter> controlar una mayor <xref:System.Windows.Controls.Panel.ZIndexProperty> que el <xref:System.Windows.Controls.Button> control.</span><span class="sxs-lookup"><span data-stu-id="25e49-111">The following example gives the <xref:System.Windows.Controls.GridSplitter> control a higher <xref:System.Windows.Controls.Panel.ZIndexProperty> than the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterZIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
-   <span data-ttu-id="25e49-112">Establezca los márgenes en el control que podría ocultar el <xref:System.Windows.Controls.GridSplitter> para que el <xref:System.Windows.Controls.GridSplitter> se expone.</span><span class="sxs-lookup"><span data-stu-id="25e49-112">Set margins on the control that would otherwise hide the <xref:System.Windows.Controls.GridSplitter> so that the <xref:System.Windows.Controls.GridSplitter> is exposed.</span></span> <span data-ttu-id="25e49-113">El ejemplo siguiente establece los márgenes de un control que en caso contrario, desea superponer y ocultar el <xref:System.Windows.Controls.GridSplitter>.</span><span class="sxs-lookup"><span data-stu-id="25e49-113">The following example sets margins on a control that would otherwise overlay and hide the <xref:System.Windows.Controls.GridSplitter>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterMargin](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## <a name="see-also"></a><span data-ttu-id="25e49-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="25e49-114">See also</span></span>

- <xref:System.Windows.Controls.GridSplitter>
- [<span data-ttu-id="25e49-115">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="25e49-115">How-to Topics</span></span>](gridsplitter-how-to-topics.md)
