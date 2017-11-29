---
title: "Cómo: Obtener el desplazamiento de un objeto Visual"
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
- getting offset values from visual objects [WPF]
- offset values [WPF], retrieving from visual objects [WPF]
- visual objects [WPF], retrieving offset values from
- retrieving offset values from visual objects [WPF]
ms.assetid: 889a1dd6-1b11-445a-b351-fbb04c53ee34
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 22c35a683f479660a17f11e44f9a0721f9d35968
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-the-offset-of-a-visual"></a>Cómo: Obtener el desplazamiento de un objeto Visual
Estos ejemplos muestran cómo recuperar el valor de desplazamiento de un objeto visual que es relativa a su elemento primario, o cualquier antecesor o descendiente.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de marcado siguiente se muestra un <xref:System.Windows.Controls.TextBlock> que se define con <xref:System.Windows.FrameworkElement.Margin%2A> valor 4.  
  
 [!code-xaml[VisualSnippets#VisualSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet1)]  
  
 En el ejemplo de código siguiente se muestra cómo utilizar el <xref:System.Windows.Media.VisualTreeHelper.GetOffset%2A> método para recuperar el desplazamiento de la <xref:System.Windows.Controls.TextBlock>. Los valores de desplazamiento se encuentran en el valor devuelto <xref:System.Windows.Vector> valor.  
  
 [!code-csharp[VisualSnippets#VisualSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet2)]
 [!code-vb[VisualSnippets#VisualSnippet2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet2)]  
  
 El desplazamiento tiene en cuenta el <xref:System.Windows.FrameworkElement.Margin%2A> valor. En este caso, <xref:System.Windows.Vector.X%2A> es 4, y <xref:System.Windows.Vector.Y%2A> es 4.  
  
 El valor de desplazamiento devuelto es relativo al elemento primario de la <xref:System.Windows.Media.Visual>. Si desea devolver un valor de desplazamiento que no es relativo al elemento primario de un <xref:System.Windows.Media.Visual>, use el <xref:System.Windows.Media.Visual.TransformToAncestor%2A> método.  
  
## <a name="getting-the-offset-relative-to-an-ancestor"></a>Obtener el desplazamiento relativo a un antecesor  
 El ejemplo de marcado siguiente se muestra un <xref:System.Windows.Controls.TextBlock> que está anidada dentro de dos <xref:System.Windows.Controls.StackPanel> objetos.  
  
 [!code-xaml[VisualSnippets#VisualSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window2.xaml#visualsnippet7)]  
  
 En la siguiente ilustración muestra el resultado del marcado.  
  
 ![Valores de desplazamiento de objetos](../../../../docs/framework/wpf/graphics-multimedia/media/visualoffset-01.png "VisualOffset_01")  
Objeto TextBlock anidado dentro de dos objetos StackPanel  
  
 En el ejemplo de código siguiente se muestra cómo utilizar el <xref:System.Windows.Media.Visual.TransformToAncestor%2A> método para recuperar el desplazamiento de la <xref:System.Windows.Controls.TextBlock> con respecto a la que contiene <xref:System.Windows.Window>. Los valores de desplazamiento se encuentran en el valor devuelto <xref:System.Windows.Media.GeneralTransform> valor.  
  
 [!code-csharp[VisualSnippets#VisualSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet5)]
 [!code-vb[VisualSnippets#VisualSnippet5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet5)]  
  
 El desplazamiento tiene en cuenta el <xref:System.Windows.FrameworkElement.Margin%2A> valores para todos los objetos dentro de la que contiene <xref:System.Windows.Window>. En este caso, <xref:System.Windows.Vector.X%2A> es 28 (16 + 8 + 4), y <xref:System.Windows.Vector.Y%2A> es 28.  
  
 El valor de desplazamiento devuelto es relativo al antecesor de la <xref:System.Windows.Media.Visual>. Si desea devolver un valor de desplazamiento que sea relativo a los descendientes de un <xref:System.Windows.Media.Visual>, use el <xref:System.Windows.Media.Visual.TransformToDescendant%2A> método.  
  
## <a name="getting-the-offset-relative-to-a-descendant"></a>Obtener el desplazamiento relativo a un descendiente  
 El ejemplo de marcado siguiente se muestra un <xref:System.Windows.Controls.TextBlock> que está dentro de un <xref:System.Windows.Controls.StackPanel> objeto.  
  
 [!code-xaml[VisualSnippets#VisualSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet4)]  
  
 En el ejemplo de código siguiente se muestra cómo utilizar el <xref:System.Windows.Media.Visual.TransformToDescendant%2A> método para recuperar el desplazamiento de la <xref:System.Windows.Controls.StackPanel> en relación con su elemento secundario <xref:System.Windows.Controls.TextBlock>. Los valores de desplazamiento se encuentran en el valor devuelto <xref:System.Windows.Media.GeneralTransform> valor.  
  
 [!code-csharp[VisualSnippets#VisualSnippet9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet9)]
 [!code-vb[VisualSnippets#VisualSnippet9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet9)]  
  
 El desplazamiento tiene en cuenta el <xref:System.Windows.FrameworkElement.Margin%2A> valores para todos los objetos. En este caso, <xref:System.Windows.Vector.X%2A> es -4, y <xref:System.Windows.Vector.Y%2A> es -4. Los valores de desplazamiento son valores negativos, puesto que el objeto primario tiene un desplazamiento negativo respecto a su objeto secundario.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.Visual>  
 <xref:System.Windows.Media.VisualTreeHelper>  
 [Información general sobre la representación de gráficos en WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)
