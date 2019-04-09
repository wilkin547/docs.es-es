---
title: Filtrar Determinar si una página se hospeda en un explorador
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosted pages in browser [WPF]
- pages [WPF], hosted in browser
ms.assetid: 737e0f26-8371-49b4-9579-70879e51e1aa
ms.openlocfilehash: d154de2f885101d1bd0c4613dfb1604be8acbe6a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107151"
---
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a><span data-ttu-id="32eee-102">Filtrar Determinar si una página se hospeda en un explorador</span><span class="sxs-lookup"><span data-stu-id="32eee-102">How to: Determine If a Page is Browser Hosted</span></span>
<span data-ttu-id="32eee-103">En este ejemplo se muestra cómo determinar si un <xref:System.Windows.Controls.Page> se hospeda en un explorador.</span><span class="sxs-lookup"><span data-stu-id="32eee-103">This example demonstrates how to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32eee-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="32eee-104">Example</span></span>  
 <span data-ttu-id="32eee-105">Un <xref:System.Windows.Controls.Page> puede ser independiente del host y, por lo tanto, se puede cargar en distintos tipos de hosts, incluidos un <xref:System.Windows.Controls.Frame>, un <xref:System.Windows.Navigation.NavigationWindow>, o en un explorador.</span><span class="sxs-lookup"><span data-stu-id="32eee-105">A <xref:System.Windows.Controls.Page> can be host agnostic and, consequently, can be loaded into several different types of hosts, including a <xref:System.Windows.Controls.Frame>, a <xref:System.Windows.Navigation.NavigationWindow>, or a browser.</span></span> <span data-ttu-id="32eee-106">Esto puede ocurrir si tiene un ensamblado de biblioteca que contiene una o varias páginas, y que se puede examinar y que se hace referencia por varios independiente ([!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]) hospedar aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="32eee-106">This can happen when you have a library assembly that contains one or more pages, and which is referenced by multiple standalone and browsable ([!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]) host applications.</span></span>  
  
 <span data-ttu-id="32eee-107">En el ejemplo siguiente se muestra cómo usar <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> para determinar si un <xref:System.Windows.Controls.Page> se hospeda en un explorador.</span><span class="sxs-lookup"><span data-stu-id="32eee-107">The following example demonstrates how to use <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a><span data-ttu-id="32eee-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="32eee-108">See also</span></span>

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
