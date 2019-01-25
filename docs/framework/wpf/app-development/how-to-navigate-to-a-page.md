---
title: Procedimiento Navegar a una página
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], navigating to
- navigation [WPF], to page
ms.assetid: 2a556fc0-748b-417f-a58a-0d05a7afb66f
ms.openlocfilehash: 7b76a12cbe6e1622e5624f5416abf24a4ca292a4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536920"
---
# <a name="how-to-navigate-to-a-page"></a><span data-ttu-id="ccc7a-102">Procedimiento Navegar a una página</span><span class="sxs-lookup"><span data-stu-id="ccc7a-102">How to: Navigate to a Page</span></span>
<span data-ttu-id="ccc7a-103">En este ejemplo se muestra varias maneras en que una página se puede navegar desde un <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="ccc7a-103">This example illustrates several ways in which a page can be navigated to from a <xref:System.Windows.Navigation.NavigationWindow>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ccc7a-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ccc7a-104">Example</span></span>  
 <span data-ttu-id="ccc7a-105">Es posible que un <xref:System.Windows.Navigation.NavigationWindow> para navegar a una página mediante uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="ccc7a-105">It is possible for a <xref:System.Windows.Navigation.NavigationWindow> to navigate to a page using one of the following:</span></span>  
  
-   <span data-ttu-id="ccc7a-106">Propiedad <xref:System.Windows.Navigation.NavigationWindow.Source%2A></span><span class="sxs-lookup"><span data-stu-id="ccc7a-106">The <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property.</span></span>  
  
-   <span data-ttu-id="ccc7a-107">El método <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> .</span><span class="sxs-lookup"><span data-stu-id="ccc7a-107">The <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> method.</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_uri#initcap#plural](../../../../includes/tlasharptla-urisharpinitcapsharpplural-md.md)] <span data-ttu-id="ccc7a-108">puede ser relativa o absoluta.</span><span class="sxs-lookup"><span data-stu-id="ccc7a-108">can be either relative or absolute.</span></span> <span data-ttu-id="ccc7a-109">Para obtener más información, vea [Empaquetar URI en WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="ccc7a-109">For more information, see [Pack URIs in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccc7a-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="ccc7a-110">See also</span></span>
- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.NavigationService>
