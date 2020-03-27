---
title: 'Cómo: Especificar una posición emergente personalizada'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: ea8d73c51dd018608b95104f00bf341ff434225c
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344950"
---
# <a name="how-to-specify-a-custom-popup-position"></a><span data-ttu-id="00533-102">Cómo: Especificar una posición emergente personalizada</span><span class="sxs-lookup"><span data-stu-id="00533-102">How to: Specify a Custom Popup Position</span></span>
<span data-ttu-id="00533-103">En este ejemplo se muestra cómo <xref:System.Windows.Controls.Primitives.Popup> especificar <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> una posición <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>personalizada para un control cuando la propiedad se establece en .</span><span class="sxs-lookup"><span data-stu-id="00533-103">This example shows how to specify a custom position for a <xref:System.Windows.Controls.Primitives.Popup> control when the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00533-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="00533-104">Example</span></span>  
 <span data-ttu-id="00533-105">Cuando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> la propiedad <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>se <xref:System.Windows.Controls.Primitives.Popup> establece en , <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> las llamadas a una instancia definida del delegado.</span><span class="sxs-lookup"><span data-stu-id="00533-105">When the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, the <xref:System.Windows.Controls.Primitives.Popup> calls a defined instance of the <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate.</span></span> <span data-ttu-id="00533-106">Este delegado devuelve un conjunto de posibles puntos que son relativos a la <xref:System.Windows.Controls.Primitives.Popup>esquina superior izquierda del área de destino y la esquina superior izquierda del archivo .</span><span class="sxs-lookup"><span data-stu-id="00533-106">This delegate returns a set of possible points that are relative to the top left corner of the target area and the top left corner of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span> <span data-ttu-id="00533-107">La <xref:System.Windows.Controls.Primitives.Popup> colocación se produce en el punto que proporciona la mejor visibilidad.</span><span class="sxs-lookup"><span data-stu-id="00533-107">The <xref:System.Windows.Controls.Primitives.Popup> placement occurs at the point that provides the best visibility.</span></span>  
  
 <span data-ttu-id="00533-108">En el ejemplo siguiente se muestra <xref:System.Windows.Controls.Primitives.Popup> cómo <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> definir <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>la posición de a estableciendo la propiedad en .</span><span class="sxs-lookup"><span data-stu-id="00533-108">The following example shows how to define the position of a <xref:System.Windows.Controls.Primitives.Popup> by setting the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span> <span data-ttu-id="00533-109">También muestra cómo crear y <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> asignar un delegado <xref:System.Windows.Controls.Primitives.Popup>para posicionar el archivo .</span><span class="sxs-lookup"><span data-stu-id="00533-109">It also shows how to create and assign a <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate in order to position the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  <span data-ttu-id="00533-110">El delegado de <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> devolución de llamada devuelve dos objetos.</span><span class="sxs-lookup"><span data-stu-id="00533-110">The callback delegate returns two <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> objects.</span></span>  <span data-ttu-id="00533-111">Si <xref:System.Windows.Controls.Primitives.Popup> el está oculto por un borde <xref:System.Windows.Controls.Primitives.Popup> de pantalla en la primera posición, el se coloca en la segunda posición.</span><span class="sxs-lookup"><span data-stu-id="00533-111">If the <xref:System.Windows.Controls.Primitives.Popup> is hidden by a screen edge at the first position, the <xref:System.Windows.Controls.Primitives.Popup> is placed at the second position.</span></span>  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 <span data-ttu-id="00533-112">Para ver el ejemplo completo, consulte Ejemplo de [ubicación emergente](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS).</span><span class="sxs-lookup"><span data-stu-id="00533-112">For the complete sample, see [Popup Placement Sample](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00533-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="00533-113">See also</span></span>

- <xref:System.Windows.Controls.Primitives.Popup>
- [<span data-ttu-id="00533-114">Información general sobre el control Popup</span><span class="sxs-lookup"><span data-stu-id="00533-114">Popup Overview</span></span>](popup-overview.md)
- [<span data-ttu-id="00533-115">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="00533-115">How-to Topics</span></span>](popup-how-to-topics.md)
