---
title: "Cómo: Desplazarse por contenido utilizando la interfaz IScrollInfo"
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
- ScrollViewer control [WPF], scrolling content
- scrolling content [WPF]
- IScrollInfo interface [WPF]
ms.assetid: d8700bef-a3f8-4c12-9de2-fc3b79f32cd3
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae6d9439ad76258105d615960bd05ecf458eb613
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-scroll-content-by-using-the-iscrollinfo-interface"></a>Cómo: Desplazarse por contenido utilizando la interfaz IScrollInfo
Este ejemplo muestra cómo desplazarse por el contenido mediante el uso de la <xref:System.Windows.Controls.Primitives.IScrollInfo> interfaz.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra las características de la <xref:System.Windows.Controls.Primitives.IScrollInfo> interfaz. El ejemplo se crea un <xref:System.Windows.Controls.StackPanel> elemento [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] que está anidada en una carpeta primaria <xref:System.Windows.Controls.ScrollViewer>. Los elementos secundarios de la <xref:System.Windows.Controls.StackPanel> se pueden desplazar lógicamente utilizando los métodos definidos por el <xref:System.Windows.Controls.Primitives.IScrollInfo> interfaz y la conversión a la instancia de <xref:System.Windows.Controls.StackPanel> (`sp1`) en el código.  
  
 [!code-xaml[IScrollInfoMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml#2)]  
  
 Cada <xref:System.Windows.Controls.Button> en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo desencadena un método personalizado asociado que controla el comportamiento de desplazamiento en <xref:System.Windows.Controls.StackPanel>. En el ejemplo siguiente se muestra cómo utilizar el <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> y <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> métodos; también genéricamente se muestra cómo usar los métodos de posición que el <xref:System.Windows.Controls.Primitives.IScrollInfo> define la clase.  
  
 [!code-csharp[IScrollInfoMethods#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.ScrollViewer>  
 <xref:System.Windows.Controls.Primitives.IScrollInfo>  
 <xref:System.Windows.Controls.StackPanel>  
 [Información general sobre ScrollViewer](../../../../docs/framework/wpf/controls/scrollviewer-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/scrollviewer-how-to-topics.md)  
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)
