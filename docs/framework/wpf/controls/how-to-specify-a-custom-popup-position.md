---
title: Procedimiento Especificar una posición emergente personalizada
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: dc516f0eb1cfcbac6662497eb4019041eefec2a9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61911214"
---
# <a name="how-to-specify-a-custom-popup-position"></a><span data-ttu-id="bca42-102">Procedimiento Especificar una posición emergente personalizada</span><span class="sxs-lookup"><span data-stu-id="bca42-102">How to: Specify a Custom Popup Position</span></span>
<span data-ttu-id="bca42-103">En este ejemplo se muestra cómo especificar una posición personalizada para un <xref:System.Windows.Controls.Primitives.Popup> controlar cuándo el <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> propiedad está establecida en <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span><span class="sxs-lookup"><span data-stu-id="bca42-103">This example shows how to specify a custom position for a <xref:System.Windows.Controls.Primitives.Popup> control when the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bca42-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bca42-104">Example</span></span>  
 <span data-ttu-id="bca42-105">Cuando el <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> propiedad está establecida en <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, <xref:System.Windows.Controls.Primitives.Popup> llama a una instancia definida de la <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegar.</span><span class="sxs-lookup"><span data-stu-id="bca42-105">When the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, the <xref:System.Windows.Controls.Primitives.Popup> calls a defined instance of the <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate.</span></span> <span data-ttu-id="bca42-106">Este delegado devuelve un conjunto de posibles puntos que son relativas a la esquina superior izquierda del área de destino y en la esquina superior izquierda de la <xref:System.Windows.Controls.Primitives.Popup>.</span><span class="sxs-lookup"><span data-stu-id="bca42-106">This delegate returns a set of possible points that are relative to the top left corner of the target area and the top left corner of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span> <span data-ttu-id="bca42-107">El <xref:System.Windows.Controls.Primitives.Popup> selección de ubicación se produce en el momento en que proporciona la mejor visibilidad.</span><span class="sxs-lookup"><span data-stu-id="bca42-107">The <xref:System.Windows.Controls.Primitives.Popup> placement occurs at the point that provides the best visibility.</span></span>  
  
 <span data-ttu-id="bca42-108">El ejemplo siguiente muestra cómo definir la posición de un <xref:System.Windows.Controls.Primitives.Popup> estableciendo el <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> propiedad <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span><span class="sxs-lookup"><span data-stu-id="bca42-108">The following example shows how to define the position of a <xref:System.Windows.Controls.Primitives.Popup> by setting the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span> <span data-ttu-id="bca42-109">También muestra cómo crear y asignar un <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegado con el fin de colocar el <xref:System.Windows.Controls.Primitives.Popup>.</span><span class="sxs-lookup"><span data-stu-id="bca42-109">It also shows how to create and assign a <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate in order to position the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  <span data-ttu-id="bca42-110">El delegado de devolución de llamada devuelve dos <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> objetos.</span><span class="sxs-lookup"><span data-stu-id="bca42-110">The callback delegate returns two <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> objects.</span></span>  <span data-ttu-id="bca42-111">Si el <xref:System.Windows.Controls.Primitives.Popup> está oculto por un borde de la pantalla en la primera posición, el <xref:System.Windows.Controls.Primitives.Popup> se coloca en la segunda posición.</span><span class="sxs-lookup"><span data-stu-id="bca42-111">If the <xref:System.Windows.Controls.Primitives.Popup> is hidden by a screen edge at the first position, the <xref:System.Windows.Controls.Primitives.Popup> is placed at the second position.</span></span>  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 <span data-ttu-id="bca42-112">Para obtener un ejemplo completo, vea [Popup Placement Sample](https://go.microsoft.com/fwlink/?LinkID=160032).</span><span class="sxs-lookup"><span data-stu-id="bca42-112">For the complete sample, see [Popup Placement Sample](https://go.microsoft.com/fwlink/?LinkID=160032).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bca42-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="bca42-113">See also</span></span>

- <xref:System.Windows.Controls.Primitives.Popup>
- [<span data-ttu-id="bca42-114">Información general sobre el control Popup</span><span class="sxs-lookup"><span data-stu-id="bca42-114">Popup Overview</span></span>](popup-overview.md)
- [<span data-ttu-id="bca42-115">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="bca42-115">How-to Topics</span></span>](popup-how-to-topics.md)
