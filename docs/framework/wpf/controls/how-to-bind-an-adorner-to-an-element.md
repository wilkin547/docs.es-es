---
title: Procedimiento Enlazar un adorno a un elemento
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UIElements [WPF], binding adorners to
- adorners [WPF], binding to specified UIElements
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
ms.openlocfilehash: b6909fec466c2b31a7f4156c43b21a0c724f0217
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62018975"
---
# <a name="how-to-bind-an-adorner-to-an-element"></a><span data-ttu-id="1f65b-102">Procedimiento Enlazar un adorno a un elemento</span><span class="sxs-lookup"><span data-stu-id="1f65b-102">How to: Bind an Adorner to an Element</span></span>
<span data-ttu-id="1f65b-103">En este ejemplo se muestra cómo enlazar mediante programación un adorno a un determinado <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="1f65b-103">This example shows how to programmatically bind an adorner to a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f65b-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f65b-104">Example</span></span>  
 <span data-ttu-id="1f65b-105">Para enlazar un adorno a un determinado <xref:System.Windows.UIElement>, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="1f65b-105">To bind an adorner to a particular <xref:System.Windows.UIElement>, follow these steps:</span></span>  
  
1. <span data-ttu-id="1f65b-106">Llame a la `static` método <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> para obtener un <xref:System.Windows.Documents.AdornerLayer> de objeto para el <xref:System.Windows.UIElement> que se va a adornar.</span><span class="sxs-lookup"><span data-stu-id="1f65b-106">Call the `static` method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to get an <xref:System.Windows.Documents.AdornerLayer> object for the <xref:System.Windows.UIElement> to be adorned.</span></span> <span data-ttu-id="1f65b-107"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> recorre el árbol visual, empezando en el índice especificado **UIElement**y devuelve la primera capa de adornos que encuentra.</span><span class="sxs-lookup"><span data-stu-id="1f65b-107"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> walks up the visual tree, starting at the specified **UIElement**, and returns the first adorner layer it finds.</span></span> <span data-ttu-id="1f65b-108">(Si no se encuentra ninguna capa de adornos, el método devuelve null).</span><span class="sxs-lookup"><span data-stu-id="1f65b-108">(If no adorner layers are found, the method returns null.)</span></span>  
  
2. <span data-ttu-id="1f65b-109">Llame a la <xref:System.Windows.Documents.AdornerLayer.Add%2A> método para enlazar el adorno al destino **UIElement**.</span><span class="sxs-lookup"><span data-stu-id="1f65b-109">Call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind the adorner to the target **UIElement**.</span></span>  
  
 <span data-ttu-id="1f65b-110">El ejemplo siguiente enlaza el adorno SimpleCircleAdorner (mostrado anteriormente) a un <xref:System.Windows.Controls.TextBox> denominado *myTextBox*.</span><span class="sxs-lookup"><span data-stu-id="1f65b-110">The following example binds a SimpleCircleAdorner (shown above) to a <xref:System.Windows.Controls.TextBox> named *myTextBox*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  <span data-ttu-id="1f65b-111">En la actualidad, no se admite el uso de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para enlazar un adorno a otro elemento.</span><span class="sxs-lookup"><span data-stu-id="1f65b-111">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f65b-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f65b-112">See also</span></span>

- [<span data-ttu-id="1f65b-113">Información general sobre adornos</span><span class="sxs-lookup"><span data-stu-id="1f65b-113">Adorners Overview</span></span>](adorners-overview.md)
