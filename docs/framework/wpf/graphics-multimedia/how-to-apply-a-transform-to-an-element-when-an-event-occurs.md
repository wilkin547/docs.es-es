---
title: Procedimiento Aplicar una transformación a un elemento cuando se produce un evento
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], transformations as event responses
- properties [WPF], LayoutTransform
- transformations as event responses [WPF]
- properties [WPF], RenderTransform
- LayoutTransform property [WPF]
ms.assetid: 71e4327e-ca57-444c-a3cf-09fb381491a0
ms.openlocfilehash: 973b9267eaef5d55176633ee80a1dc7f8b043909
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698998"
---
# <a name="how-to-apply-a-transform-to-an-element-when-an-event-occurs"></a><span data-ttu-id="fab3f-102">Procedimiento Aplicar una transformación a un elemento cuando se produce un evento</span><span class="sxs-lookup"><span data-stu-id="fab3f-102">How to: Apply a Transform to an Element When an Event Occurs</span></span>
<span data-ttu-id="fab3f-103">En este ejemplo se muestra cómo aplicar un <xref:System.Windows.Media.ScaleTransform> cuando se produce un evento.</span><span class="sxs-lookup"><span data-stu-id="fab3f-103">This example shows how to apply a <xref:System.Windows.Media.ScaleTransform> when an event occurs.</span></span> <span data-ttu-id="fab3f-104">El concepto que se muestra aquí es el mismo que se utiliza para aplicar otros tipos de transformaciones.</span><span class="sxs-lookup"><span data-stu-id="fab3f-104">The concept that is shown here is the same that you use for applying other types of transformations.</span></span> <span data-ttu-id="fab3f-105">Para obtener más información acerca de los tipos de transformaciones disponibles, consulte el <xref:System.Windows.Media.Transform> clase o [información general sobre transformaciones](transforms-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fab3f-105">For more information about the available types of transformations, see the <xref:System.Windows.Media.Transform> class or [Transforms Overview](transforms-overview.md).</span></span>  
  
 <span data-ttu-id="fab3f-106">Puede aplicar una transformación a un elemento de cualquiera de estas dos maneras:</span><span class="sxs-lookup"><span data-stu-id="fab3f-106">You can apply a transform to an element in either of these two ways:</span></span>  
  
- <span data-ttu-id="fab3f-107">Si lo hace *no* desea que la transformación afecte al diseño, utilice el <xref:System.Windows.UIElement.RenderTransform%2A> propiedad del elemento.</span><span class="sxs-lookup"><span data-stu-id="fab3f-107">If you do *not* want the transform to affect layout, use the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span>  
  
- <span data-ttu-id="fab3f-108">Si desea que la transformación afecte al diseño, utilice el <xref:System.Windows.FrameworkElement.LayoutTransform%2A> propiedad del elemento.</span><span class="sxs-lookup"><span data-stu-id="fab3f-108">If you do want the transform to affect layout, use the <xref:System.Windows.FrameworkElement.LayoutTransform%2A> property of the element.</span></span>  
  
 <span data-ttu-id="fab3f-109">El ejemplo siguiente aplica un <xref:System.Windows.Media.ScaleTransform> a la <xref:System.Windows.UIElement.RenderTransform%2A> propiedad de un botón.</span><span class="sxs-lookup"><span data-stu-id="fab3f-109">The following example applies a <xref:System.Windows.Media.ScaleTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of a button.</span></span> <span data-ttu-id="fab3f-110">Cuando se mueve el mouse sobre el botón, el <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> y <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> propiedades de la <xref:System.Windows.Media.ScaleTransform> se establecen en `2`, lo que hace que el botón se agrande.</span><span class="sxs-lookup"><span data-stu-id="fab3f-110">When the mouse moves over the button, the <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> properties of the <xref:System.Windows.Media.ScaleTransform> are set to `2`, which causes the button to become larger.</span></span> <span data-ttu-id="fab3f-111">Cuando el mouse se aleja del botón, <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> y <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> se establecen en `1`, lo que hace que el botón para volver a su tamaño original.</span><span class="sxs-lookup"><span data-stu-id="fab3f-111">When the mouse moves off the button, <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> are set to `1`, which causes the button to return to its original size.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fab3f-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fab3f-112">Example</span></span>  
 [!code-xaml[ButtonTransform#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml#1)]  
  
 [!code-csharp[ButtonTransform#1cb](~/samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml.cs#1cb)]
 [!code-vb[ButtonTransform#1cb](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ButtonTransform/VisualBasic/ButtonTransformExample.xaml.vb#1cb)]  
  
## <a name="see-also"></a><span data-ttu-id="fab3f-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="fab3f-113">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [<span data-ttu-id="fab3f-114">Información general sobre transformaciones</span><span class="sxs-lookup"><span data-stu-id="fab3f-114">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="fab3f-115">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="fab3f-115">How-to Topics</span></span>](transformations-how-to-topics.md)
- [<span data-ttu-id="fab3f-116">Información general sobre eventos enrutados</span><span class="sxs-lookup"><span data-stu-id="fab3f-116">Routed Events Overview</span></span>](../advanced/routed-events-overview.md)
