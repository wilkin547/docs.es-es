---
title: "Cómo: determinar si una página está hospedada de explorador"
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
helpviewer_keywords:
- hosted pages in browser [WPF]
- pages [WPF], hosted in browser
ms.assetid: 737e0f26-8371-49b4-9579-70879e51e1aa
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dd8a8b8c3bea291afbe41e0c36e0d708bff3ef57
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a>Cómo: determinar si una página está hospedada de explorador
En este ejemplo se muestra cómo determinar si un <xref:System.Windows.Controls.Page> se hospeda en un explorador.  
  
## <a name="example"></a>Ejemplo  
 A <xref:System.Windows.Controls.Page> puede ser independiente del host y, por lo tanto, se puede cargar en distintos tipos de hosts, incluidos un <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Navigation.NavigationWindow>, o en un explorador. Esto puede ocurrir si tiene un ensamblado de biblioteca que contiene una o varias páginas y que está referenciado por varios independiente y permite la exploración ([!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]) hospedar aplicaciones.  
  
 En el ejemplo siguiente se muestra cómo usar <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> para determinar si un <xref:System.Windows.Controls.Page> se hospeda en un explorador.  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.Frame>  
 <xref:System.Windows.Controls.Page>
