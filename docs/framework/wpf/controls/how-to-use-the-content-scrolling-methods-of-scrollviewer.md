---
title: 'Cómo: Utilizar los métodos de desplazamiento de contenido de ScrollViewer'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- IScrollInfo interface [WPF]
- scrolling methods [WPF]
- ScrollViewer control [WPF], scrolling methods
ms.assetid: 4708cc65-6510-45f8-82e6-30b0d3e30045
ms.openlocfilehash: b4da666934be7dd182838d870e54e496b2646901
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552771"
---
# <a name="how-to-use-the-content-scrolling-methods-of-scrollviewer"></a><span data-ttu-id="3dcfe-102">Cómo: Utilizar los métodos de desplazamiento de contenido de ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="3dcfe-102">How to: Use the Content-Scrolling Methods of ScrollViewer</span></span>
<span data-ttu-id="3dcfe-103">Este ejemplo muestra cómo utilizar los métodos de desplazamiento de la <xref:System.Windows.Controls.ScrollViewer> elemento.</span><span class="sxs-lookup"><span data-stu-id="3dcfe-103">This example shows how to use the scrolling methods of the <xref:System.Windows.Controls.ScrollViewer> element.</span></span> <span data-ttu-id="3dcfe-104">Estos métodos proporcionan incremental desplazamiento de contenido, ya sea por línea o por página, en un <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="3dcfe-104">These methods provide incremental scrolling of content, either by line or by page, in a <xref:System.Windows.Controls.ScrollViewer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3dcfe-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3dcfe-105">Example</span></span>  
 <span data-ttu-id="3dcfe-106">En el ejemplo siguiente se crea un <xref:System.Windows.Controls.ScrollViewer> denominado `sv1`, que hospeda un elemento secundario <xref:System.Windows.Controls.TextBlock> elemento.</span><span class="sxs-lookup"><span data-stu-id="3dcfe-106">The following example creates a <xref:System.Windows.Controls.ScrollViewer> named `sv1`, which hosts a child <xref:System.Windows.Controls.TextBlock> element.</span></span> <span data-ttu-id="3dcfe-107">Dado que la <xref:System.Windows.Controls.TextBlock> es mayor que el elemento primario <xref:System.Windows.Controls.ScrollViewer>, aparecen barras de desplazamiento con el fin de habilitar el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="3dcfe-107">Because the <xref:System.Windows.Controls.TextBlock> is larger than the parent <xref:System.Windows.Controls.ScrollViewer>, scroll bars appear in order to enable scrolling.</span></span> <span data-ttu-id="3dcfe-108"><xref:System.Windows.Controls.Button> elementos que representan los distintos métodos de desplazamiento se acoplan a la izquierda en otro <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="3dcfe-108"><xref:System.Windows.Controls.Button> elements that represent the various scrolling methods are docked on the left in a separate <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="3dcfe-109">Cada <xref:System.Windows.Controls.Button> en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo llama a un método personalizado relacionado que controla el comportamiento de desplazamiento en <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="3dcfe-109">Each <xref:System.Windows.Controls.Button> in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file calls a related custom method that controls scrolling behavior in <xref:System.Windows.Controls.ScrollViewer>.</span></span>  
  
 [!code-xaml[ScrollViewerMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="3dcfe-110">En el ejemplo siguiente se usa el <xref:System.Windows.Controls.ScrollViewer.LineUp%2A> y <xref:System.Windows.Controls.ScrollViewer.LineDown%2A> métodos.</span><span class="sxs-lookup"><span data-stu-id="3dcfe-110">The following example uses the <xref:System.Windows.Controls.ScrollViewer.LineUp%2A> and <xref:System.Windows.Controls.ScrollViewer.LineDown%2A> methods.</span></span>  
  
 [!code-csharp[ScrollViewerMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ScrollViewerMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewerMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="3dcfe-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="3dcfe-111">See Also</span></span>  
 <xref:System.Windows.Controls.ScrollViewer>  
 <xref:System.Windows.Controls.StackPanel>
