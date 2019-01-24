---
title: Procedimiento Determinar si una página está hospedada de explorador
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosted pages in browser [WPF]
- pages [WPF], hosted in browser
ms.assetid: 737e0f26-8371-49b4-9579-70879e51e1aa
ms.openlocfilehash: aa2aa36e4f887c4fa02314f7834e2a46268c8ff9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661300"
---
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a>Procedimiento Determinar si una página está hospedada de explorador
En este ejemplo se muestra cómo determinar si un <xref:System.Windows.Controls.Page> se hospeda en un explorador.  
  
## <a name="example"></a>Ejemplo  
 Un <xref:System.Windows.Controls.Page> puede ser independiente del host y, por lo tanto, se puede cargar en distintos tipos de hosts, incluidos un <xref:System.Windows.Controls.Frame>, un <xref:System.Windows.Navigation.NavigationWindow>, o en un explorador. Esto puede ocurrir si tiene un ensamblado de biblioteca que contiene una o varias páginas, y que se puede examinar y que se hace referencia por varios independiente ([!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]) hospedar aplicaciones.  
  
 En el ejemplo siguiente se muestra cómo usar <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> para determinar si un <xref:System.Windows.Controls.Page> se hospeda en un explorador.  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
