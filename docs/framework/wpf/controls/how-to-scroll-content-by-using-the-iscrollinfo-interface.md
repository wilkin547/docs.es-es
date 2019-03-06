---
title: Filtrar Desplazarse por contenido utilizando la interfaz IScrollInfo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ScrollViewer control [WPF], scrolling content
- scrolling content [WPF]
- IScrollInfo interface [WPF]
ms.assetid: d8700bef-a3f8-4c12-9de2-fc3b79f32cd3
ms.openlocfilehash: 145c58064b8557f9cb4730ec9272c354c7aa9c1b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378983"
---
# <a name="how-to-scroll-content-by-using-the-iscrollinfo-interface"></a>Filtrar Desplazarse por contenido utilizando la interfaz IScrollInfo
En este ejemplo se muestra cómo desplazarse por contenido utilizando la <xref:System.Windows.Controls.Primitives.IScrollInfo> interfaz.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra las características de la <xref:System.Windows.Controls.Primitives.IScrollInfo> interfaz. El ejemplo se crea un <xref:System.Windows.Controls.StackPanel> elemento [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] que está anidado en un elemento primario <xref:System.Windows.Controls.ScrollViewer>. Los elementos secundarios de la <xref:System.Windows.Controls.StackPanel> se puede desplazar de forma lógica mediante el uso de los métodos definidos por el <xref:System.Windows.Controls.Primitives.IScrollInfo> interfaz y la conversión a la instancia de <xref:System.Windows.Controls.StackPanel> (`sp1`) en el código.  
  
 [!code-xaml[IScrollInfoMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml#2)]  
  
 Cada <xref:System.Windows.Controls.Button> en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo desencadena un método personalizado asociado que controla el comportamiento de desplazamiento en <xref:System.Windows.Controls.StackPanel>. El ejemplo siguiente muestra cómo usar el <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> y <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> métodos; genéricamente también se muestra cómo usar los métodos de posición que el <xref:System.Windows.Controls.Primitives.IScrollInfo> define la clase.  
  
 [!code-csharp[IScrollInfoMethods#3](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- <xref:System.Windows.Controls.StackPanel>
- [Información general sobre ScrollViewer](scrollviewer-overview.md)
- [Temas "Cómo..."](scrollviewer-how-to-topics.md)
- [Información general sobre elementos Panel](panels-overview.md)
