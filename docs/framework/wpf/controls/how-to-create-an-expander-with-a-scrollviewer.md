---
title: Procedimiento Crear un control Expander con un control ScrollViewer
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Expander
- ScrollViewer control [WPF], with Expander control
- Expander control [WPF], creating
- controls [WPF], ScrollViewer
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
ms.openlocfilehash: ef0bc5d344f7d465de9209708430d3e61d40d4f7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59114655"
---
# <a name="how-to-create-an-expander-with-a-scrollviewer"></a><span data-ttu-id="e4a14-102">Procedimiento Crear un control Expander con un control ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="e4a14-102">How to: Create an Expander with a ScrollViewer</span></span>
<span data-ttu-id="e4a14-103">En este ejemplo se muestra cómo crear un <xref:System.Windows.Controls.Expander> control que contiene contenido complejo, como una imagen y texto.</span><span class="sxs-lookup"><span data-stu-id="e4a14-103">This example shows how to create an <xref:System.Windows.Controls.Expander> control that contains complex content, such as an image and text.</span></span> <span data-ttu-id="e4a14-104">El ejemplo también incluye el contenido de la <xref:System.Windows.Controls.Expander> en un <xref:System.Windows.Controls.ScrollViewer> control.</span><span class="sxs-lookup"><span data-stu-id="e4a14-104">The example also encloses the content of the <xref:System.Windows.Controls.Expander> in a <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4a14-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e4a14-105">Example</span></span>  
 <span data-ttu-id="e4a14-106">El ejemplo siguiente muestra cómo crear un <xref:System.Windows.Controls.Expander>.</span><span class="sxs-lookup"><span data-stu-id="e4a14-106">The following example shows how to create an <xref:System.Windows.Controls.Expander>.</span></span> <span data-ttu-id="e4a14-107">El ejemplo se usa un <xref:System.Windows.Controls.Primitives.BulletDecorator> control, que contiene una imagen y texto, con el fin de definir el <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>.</span><span class="sxs-lookup"><span data-stu-id="e4a14-107">The example uses a <xref:System.Windows.Controls.Primitives.BulletDecorator> control, which contains an image and text, in order to define the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>.</span></span> <span data-ttu-id="e4a14-108">Un <xref:System.Windows.Controls.ScrollViewer> control proporciona un método para desplazar el contenido expandido.</span><span class="sxs-lookup"><span data-stu-id="e4a14-108">A <xref:System.Windows.Controls.ScrollViewer> control provides a method for scrolling the expanded content.</span></span>  
  
 <span data-ttu-id="e4a14-109">Tenga en cuenta que el ejemplo establece la <xref:System.Windows.FrameworkElement.Height%2A> propiedad en el <xref:System.Windows.Controls.ScrollViewer> en lugar de en el contenido.</span><span class="sxs-lookup"><span data-stu-id="e4a14-109">Note that the example sets the <xref:System.Windows.FrameworkElement.Height%2A> property on the <xref:System.Windows.Controls.ScrollViewer> instead of on the content.</span></span> <span data-ttu-id="e4a14-110">Si el <xref:System.Windows.FrameworkElement.Height%2A> se establece en el contenido, el <xref:System.Windows.Controls.ScrollViewer> no permite al usuario desplazar el contenido.</span><span class="sxs-lookup"><span data-stu-id="e4a14-110">If the <xref:System.Windows.FrameworkElement.Height%2A> is set on the content, the <xref:System.Windows.Controls.ScrollViewer> does not allow the user to scroll the content.</span></span> <span data-ttu-id="e4a14-111">El <xref:System.Windows.FrameworkElement.Width%2A> propiedad está establecida en el <xref:System.Windows.Controls.Expander> control y esta configuración se aplica a la <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> y el contenido expandido.</span><span class="sxs-lookup"><span data-stu-id="e4a14-111">The <xref:System.Windows.FrameworkElement.Width%2A> property is set on the <xref:System.Windows.Controls.Expander> control and this setting applies to the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the expanded content.</span></span>  
  
 [!code-xaml[ExpanderRichContent#CreateExpander](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## <a name="see-also"></a><span data-ttu-id="e4a14-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4a14-112">See also</span></span>

- <xref:System.Windows.Controls.Expander>
- [<span data-ttu-id="e4a14-113">Información general sobre el control Expander</span><span class="sxs-lookup"><span data-stu-id="e4a14-113">Expander Overview</span></span>](expander-overview.md)
- [<span data-ttu-id="e4a14-114">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="e4a14-114">How-to Topics</span></span>](expander-how-to-topics.md)
