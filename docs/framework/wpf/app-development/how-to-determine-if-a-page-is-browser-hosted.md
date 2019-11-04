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
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a>Cómo: determinar si una página está hospedada en un explorador
En este ejemplo se muestra cómo determinar si una <xref:System.Windows.Controls.Page> está hospedada en un explorador.  
  
## <a name="example"></a>Ejemplo  
 Un <xref:System.Windows.Controls.Page> puede ser independiente del host y, por consiguiente, se puede cargar en varios tipos diferentes de hosts, entre los que se incluyen un <xref:System.Windows.Controls.Frame>, un <xref:System.Windows.Navigation.NavigationWindow>o un explorador. Esto puede ocurrir cuando tiene un ensamblado de biblioteca que contiene una o más páginas y al que se hace referencia en varias aplicaciones host independientes y explorables (aplicación de explorador XAML (XBAP)).  
  
 En el ejemplo siguiente se muestra cómo usar <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> para determinar si un <xref:System.Windows.Controls.Page> está hospedado en un explorador.  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
