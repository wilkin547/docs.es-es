---
title: 'Cómo: navegar a una página'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], navigating to
- navigation [WPF], to page
ms.assetid: 2a556fc0-748b-417f-a58a-0d05a7afb66f
ms.openlocfilehash: 25a0dbbc609c7b6f8f2878d2068e61e492a59c7e
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582539"
---
# <a name="how-to-navigate-to-a-page"></a>Cómo: navegar a una página
En este ejemplo se muestran varias maneras en las que se puede navegar a una página desde un <xref:System.Windows.Navigation.NavigationWindow>.  
  
## <a name="example"></a>Ejemplo  
 Es posible que una <xref:System.Windows.Navigation.NavigationWindow> navegue hasta una página mediante una de las siguientes acciones:  
  
- Propiedad <xref:System.Windows.Navigation.NavigationWindow.Source%2A>  
  
- El método <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> .  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
> Los identificadores uniformes de recursos (URI) pueden ser relativos o absolutos. Para obtener más información, vea [Empaquetar URI en WPF](pack-uris-in-wpf.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.NavigationService>
