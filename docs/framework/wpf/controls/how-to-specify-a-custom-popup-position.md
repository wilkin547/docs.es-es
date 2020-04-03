---
title: 'Cómo: Especificar una posición emergente personalizada'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: b48dedc044b418062642af5c5bb40afab78a3c97
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635747"
---
# <a name="how-to-specify-a-custom-popup-position"></a><span data-ttu-id="fb025-102">Cómo: Especificar una posición emergente personalizada</span><span class="sxs-lookup"><span data-stu-id="fb025-102">How to: Specify a Custom Popup Position</span></span>
<span data-ttu-id="fb025-103">En este ejemplo se muestra cómo <xref:System.Windows.Controls.Primitives.Popup> especificar <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> una posición <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>personalizada para un control cuando la propiedad se establece en .</span><span class="sxs-lookup"><span data-stu-id="fb025-103">This example shows how to specify a custom position for a <xref:System.Windows.Controls.Primitives.Popup> control when the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb025-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fb025-104">Example</span></span>  
 <span data-ttu-id="fb025-105">Cuando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> la propiedad <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>se <xref:System.Windows.Controls.Primitives.Popup> establece en , <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> las llamadas a una instancia definida del delegado.</span><span class="sxs-lookup"><span data-stu-id="fb025-105">When the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, the <xref:System.Windows.Controls.Primitives.Popup> calls a defined instance of the <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate.</span></span> <span data-ttu-id="fb025-106">Este delegado devuelve un conjunto de posibles puntos que son relativos a la esquina <xref:System.Windows.Controls.Primitives.Popup>superior izquierda del área de destino y la esquina superior izquierda del archivo .</span><span class="sxs-lookup"><span data-stu-id="fb025-106">This delegate returns a set of possible points that are relative to the top-left corner of the target area and the top-left corner of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span> <span data-ttu-id="fb025-107">La <xref:System.Windows.Controls.Primitives.Popup> colocación se produce en el punto que proporciona la mejor visibilidad.</span><span class="sxs-lookup"><span data-stu-id="fb025-107">The <xref:System.Windows.Controls.Primitives.Popup> placement occurs at the point that provides the best visibility.</span></span>  
  
 <span data-ttu-id="fb025-108">En el ejemplo siguiente se muestra <xref:System.Windows.Controls.Primitives.Popup> cómo <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> definir <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>la posición de a estableciendo la propiedad en .</span><span class="sxs-lookup"><span data-stu-id="fb025-108">The following example shows how to define the position of a <xref:System.Windows.Controls.Primitives.Popup> by setting the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span> <span data-ttu-id="fb025-109">También muestra cómo crear y <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> asignar un delegado <xref:System.Windows.Controls.Primitives.Popup>para posicionar el archivo .</span><span class="sxs-lookup"><span data-stu-id="fb025-109">It also shows how to create and assign a <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate in order to position the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  <span data-ttu-id="fb025-110">El delegado de <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> devolución de llamada devuelve dos objetos.</span><span class="sxs-lookup"><span data-stu-id="fb025-110">The callback delegate returns two <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> objects.</span></span>  <span data-ttu-id="fb025-111">Si <xref:System.Windows.Controls.Primitives.Popup> el está oculto por un borde <xref:System.Windows.Controls.Primitives.Popup> de pantalla en la primera posición, el se coloca en la segunda posición.</span><span class="sxs-lookup"><span data-stu-id="fb025-111">If the <xref:System.Windows.Controls.Primitives.Popup> is hidden by a screen edge at the first position, the <xref:System.Windows.Controls.Primitives.Popup> is placed at the second position.</span></span>  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 <span data-ttu-id="fb025-112">Para ver el ejemplo completo, consulte Ejemplo de [ubicación emergente](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS).</span><span class="sxs-lookup"><span data-stu-id="fb025-112">For the complete sample, see [Popup Placement Sample](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb025-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb025-113">See also</span></span>

- <xref:System.Windows.Controls.Primitives.Popup>
- [<span data-ttu-id="fb025-114">Descripción general de Popup</span><span class="sxs-lookup"><span data-stu-id="fb025-114">Popup overview</span></span>](popup-overview.md)
- [<span data-ttu-id="fb025-115">Artículos de información como</span><span class="sxs-lookup"><span data-stu-id="fb025-115">How-to articles</span></span>](popup-how-to-topics.md)
