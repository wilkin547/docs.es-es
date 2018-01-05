---
title: "Cómo: Especificar el subrayado de un hipervínculo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: Hyperlink control type [WPF]
ms.assetid: 3996cfe6-1dac-4835-aeb3-c719ce9cfee5
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 24c3cc1bba4fd12d4a0f2ad02fa0c1b52b124381
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-whether-a-hyperlink-is-underlined"></a><span data-ttu-id="7736b-102">Cómo: Especificar el subrayado de un hipervínculo</span><span class="sxs-lookup"><span data-stu-id="7736b-102">How to: Specify Whether a Hyperlink is Underlined</span></span>
<span data-ttu-id="7736b-103">La <xref:System.Windows.Documents.Hyperlink> objeto es un elemento de contenido dinámico insertado que permite hospedar hipervínculos dentro del contenido dinámico.</span><span class="sxs-lookup"><span data-stu-id="7736b-103">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="7736b-104">De forma predeterminada, <xref:System.Windows.Documents.Hyperlink> utiliza un <xref:System.Windows.TextDecoration> objeto para mostrar un subrayado.</span><span class="sxs-lookup"><span data-stu-id="7736b-104">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="7736b-105"><xref:System.Windows.TextDecoration>los objetos pueden ser mejorar el rendimiento al crear instancias, especialmente si tiene muchos <xref:System.Windows.Documents.Hyperlink> objetos.</span><span class="sxs-lookup"><span data-stu-id="7736b-105"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="7736b-106">Si realiza uso extenso de <xref:System.Windows.Documents.Hyperlink> elementos, puede que desee tener en cuenta que muestra un subrayado únicamente al desencadenar un evento, como el <xref:System.Windows.ContentElement.MouseEnter> eventos.</span><span class="sxs-lookup"><span data-stu-id="7736b-106">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="7736b-107">En el ejemplo siguiente, el subrayado para el vínculo "My MSN" es dinámico, solo aparece cuando la <xref:System.Windows.ContentElement.MouseEnter> evento se desencadena.</span><span class="sxs-lookup"><span data-stu-id="7736b-107">In the following example, the underline for the "My MSN" link is dynamic—it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
 <span data-ttu-id="7736b-108">![Hipervínculos que muestran TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")</span><span class="sxs-lookup"><span data-stu-id="7736b-108">![Hyperlinks displaying TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")</span></span>  
<span data-ttu-id="7736b-109">Hipervínculos definidos con TextDecorations</span><span class="sxs-lookup"><span data-stu-id="7736b-109">Hyperlinks defined with TextDecorations</span></span>  
  
## <a name="example"></a><span data-ttu-id="7736b-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7736b-110">Example</span></span>  
 <span data-ttu-id="7736b-111">El ejemplo de marcado siguiente se muestra un <xref:System.Windows.Documents.Hyperlink> definido con y sin un subrayado:</span><span class="sxs-lookup"><span data-stu-id="7736b-111">The following markup sample shows a <xref:System.Windows.Documents.Hyperlink> defined with and without an underline:</span></span>  
  
 [!code-xaml[Performance#PerformanceSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 <span data-ttu-id="7736b-112">El ejemplo de código siguiente muestra cómo crear un subrayado para el <xref:System.Windows.Documents.Hyperlink> en el <xref:System.Windows.ContentElement.MouseEnter> eventos y quitar en el <xref:System.Windows.ContentElement.MouseLeave> eventos.</span><span class="sxs-lookup"><span data-stu-id="7736b-112">The following code sample shows how to create an underline for the <xref:System.Windows.Documents.Hyperlink> on the <xref:System.Windows.ContentElement.MouseEnter> event, and remove it on the <xref:System.Windows.ContentElement.MouseLeave> event.</span></span>  
  
 [!code-csharp[Performance#PerformanceSnippet15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml.cs#performancesnippet15)]
 [!code-vb[Performance#PerformanceSnippet15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/hyperlink.xaml.vb#performancesnippet15)]  
  
## <a name="see-also"></a><span data-ttu-id="7736b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="7736b-113">See Also</span></span>  
 <xref:System.Windows.TextDecoration>  
 <xref:System.Windows.Documents.Hyperlink>  
 [<span data-ttu-id="7736b-114">Optimizar WPF: Rendimiento de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="7736b-114">Optimizing WPF Application Performance</span></span>](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [<span data-ttu-id="7736b-115">Crear una decoración de texto</span><span class="sxs-lookup"><span data-stu-id="7736b-115">Create a Text Decoration</span></span>](../../../../docs/framework/wpf/advanced/how-to-create-a-text-decoration.md)
