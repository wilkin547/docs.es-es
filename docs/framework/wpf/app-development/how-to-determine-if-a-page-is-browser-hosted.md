---
title: 'Cómo: determinar si una página está hospedada en un explorador'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosted pages in browser [WPF]
- pages [WPF], hosted in browser
ms.assetid: 737e0f26-8371-49b4-9579-70879e51e1aa
ms.openlocfilehash: c4cb1065807d16c1d1f5a95c8ac9c9cbe5a0fdab
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424690"
---
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a><span data-ttu-id="5123f-102">Cómo: determinar si una página está hospedada en un explorador</span><span class="sxs-lookup"><span data-stu-id="5123f-102">How to: Determine If a Page is Browser Hosted</span></span>
<span data-ttu-id="5123f-103">En este ejemplo se muestra cómo determinar si una <xref:System.Windows.Controls.Page> está hospedada en un explorador.</span><span class="sxs-lookup"><span data-stu-id="5123f-103">This example demonstrates how to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5123f-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5123f-104">Example</span></span>  
 <span data-ttu-id="5123f-105">Un <xref:System.Windows.Controls.Page> puede ser independiente del host y, por consiguiente, se puede cargar en varios tipos diferentes de hosts, entre los que se incluyen un <xref:System.Windows.Controls.Frame>, un <xref:System.Windows.Navigation.NavigationWindow>o un explorador.</span><span class="sxs-lookup"><span data-stu-id="5123f-105">A <xref:System.Windows.Controls.Page> can be host agnostic and, consequently, can be loaded into several different types of hosts, including a <xref:System.Windows.Controls.Frame>, a <xref:System.Windows.Navigation.NavigationWindow>, or a browser.</span></span> <span data-ttu-id="5123f-106">Esto puede ocurrir cuando tiene un ensamblado de biblioteca que contiene una o más páginas y al que se hace referencia en varias aplicaciones host independientes y explorables (aplicación de explorador XAML (XBAP)).</span><span class="sxs-lookup"><span data-stu-id="5123f-106">This can happen when you have a library assembly that contains one or more pages, and which is referenced by multiple standalone and browsable (XAML browser application (XBAP)) host applications.</span></span>  
  
 <span data-ttu-id="5123f-107">En el ejemplo siguiente se muestra cómo usar <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> para determinar si un <xref:System.Windows.Controls.Page> está hospedado en un explorador.</span><span class="sxs-lookup"><span data-stu-id="5123f-107">The following example demonstrates how to use <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a><span data-ttu-id="5123f-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="5123f-108">See also</span></span>

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
