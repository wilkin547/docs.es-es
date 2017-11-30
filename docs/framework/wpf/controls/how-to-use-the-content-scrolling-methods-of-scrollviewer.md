---
title: "Cómo: Utilizar los métodos de desplazamiento de contenido de ScrollViewer"
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
- IScrollInfo interface [WPF]
- scrolling methods [WPF]
- ScrollViewer control [WPF], scrolling methods
ms.assetid: 4708cc65-6510-45f8-82e6-30b0d3e30045
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dc9b79ae9b8078bbdc4c41fb0c952237f86fcac8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-content-scrolling-methods-of-scrollviewer"></a>Cómo: Utilizar los métodos de desplazamiento de contenido de ScrollViewer
Este ejemplo muestra cómo utilizar los métodos de desplazamiento de la <xref:System.Windows.Controls.ScrollViewer> elemento. Estos métodos proporcionan incremental desplazamiento de contenido, ya sea por línea o por página, en un <xref:System.Windows.Controls.ScrollViewer>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un <xref:System.Windows.Controls.ScrollViewer> denominado `sv1`, que hospeda un elemento secundario <xref:System.Windows.Controls.TextBlock> elemento. Dado que la <xref:System.Windows.Controls.TextBlock> es mayor que el elemento primario <xref:System.Windows.Controls.ScrollViewer>, aparecen barras de desplazamiento con el fin de habilitar el desplazamiento. <xref:System.Windows.Controls.Button>elementos que representan los distintos métodos de desplazamiento se acoplan a la izquierda en otro <xref:System.Windows.Controls.StackPanel>. Cada <xref:System.Windows.Controls.Button> en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo llama a un método personalizado relacionado que controla el comportamiento de desplazamiento en <xref:System.Windows.Controls.ScrollViewer>.  
  
 [!code-xaml[ScrollViewerMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml#1)]  
  
 En el ejemplo siguiente se usa el <xref:System.Windows.Controls.ScrollViewer.LineUp%2A> y <xref:System.Windows.Controls.ScrollViewer.LineDown%2A> métodos.  
  
 [!code-csharp[ScrollViewerMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ScrollViewerMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewerMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.ScrollViewer>  
 <xref:System.Windows.Controls.StackPanel>
