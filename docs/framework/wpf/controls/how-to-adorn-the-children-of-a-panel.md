---
title: 'Cómo: Incluir adornos en los elementos secundarios de un panel'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
ms.openlocfilehash: 4babbf1df57f340a3f6be218f213ad1c868ec9f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33550224"
---
# <a name="how-to-adorn-the-children-of-a-panel"></a><span data-ttu-id="b2787-102">Cómo: Incluir adornos en los elementos secundarios de un panel</span><span class="sxs-lookup"><span data-stu-id="b2787-102">How to: Adorn the Children of a Panel</span></span>
<span data-ttu-id="b2787-103">Este ejemplo muestra cómo enlazar mediante programación un adorno a los elementos secundarios de un determinado <xref:System.Windows.Controls.Panel>.</span><span class="sxs-lookup"><span data-stu-id="b2787-103">This example shows how to programmatically bind an adorner to the children of a specified <xref:System.Windows.Controls.Panel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2787-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b2787-104">Example</span></span>  
 <span data-ttu-id="b2787-105">Para enlazar un adorno a los elementos secundarios de un <xref:System.Windows.Controls.Panel>, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b2787-105">To bind an adorner to the children of a <xref:System.Windows.Controls.Panel>, follow these steps:</span></span>  
  
1.  <span data-ttu-id="b2787-106">Declarar un nuevo <xref:System.Windows.Documents.AdornerLayer> objeto y llame al método el `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> método para buscar una capa de adornos para el elemento cuyos elementos secundarios se van a etiquetar.</span><span class="sxs-lookup"><span data-stu-id="b2787-106">Declare a new <xref:System.Windows.Documents.AdornerLayer> object and call the `static`<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> method to find an adorner layer for the element whose children are to be adorned.</span></span>  
  
2.  <span data-ttu-id="b2787-107">Enumerar los elementos secundarios del elemento primario y llamada la <xref:System.Windows.Documents.AdornerLayer.Add%2A> método para enlazar un adorno a cada elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="b2787-107">Enumerate through the children of the parent element and call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind an adorner to each child element.</span></span>  
  
 <span data-ttu-id="b2787-108">En el ejemplo siguiente se enlaza la etiqueta contextual SimpleCircleAdorner (mostrada anteriormente) a los elementos secundarios de un <xref:System.Windows.Controls.StackPanel> denominado *myStackPanel*.</span><span class="sxs-lookup"><span data-stu-id="b2787-108">The following example binds a SimpleCircleAdorner (shown above) to the children of a <xref:System.Windows.Controls.StackPanel> named *myStackPanel*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
>  <span data-ttu-id="b2787-109">En la actualidad, no se admite el uso de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para enlazar un adorno a otro elemento.</span><span class="sxs-lookup"><span data-stu-id="b2787-109">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2787-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2787-110">See Also</span></span>  
 [<span data-ttu-id="b2787-111">Información general sobre adornos</span><span class="sxs-lookup"><span data-stu-id="b2787-111">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
