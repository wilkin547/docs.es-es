---
title: 'Cómo: Animar el tamaño de un elemento FrameworkElement'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], FrameworkElement size
- FrameworkElement [WPF], animating size of
ms.assetid: d4cd5a13-c20d-4a6f-a2ba-14f2c9ce4cef
ms.openlocfilehash: 148e3d592e129984bd2f7ac062340c5169e48d30
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543990"
---
# <a name="how-to-animate-the-size-of-a-frameworkelement"></a>Cómo: Animar el tamaño de un elemento FrameworkElement
Animar el tamaño de un <xref:System.Windows.FrameworkElement>, o bien puede animar su <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades o use un elemento animado <xref:System.Windows.Media.ScaleTransform>.  
  
 En el ejemplo siguiente anima el tamaño de dos botones utilizando estos dos enfoques. Se cambia el tamaño de un botón animando su <xref:System.Windows.FrameworkElement.Width%2A> se cambia el tamaño de propiedad y otro animando un <xref:System.Windows.Media.ScaleTransform> aplica a su <xref:System.Windows.UIElement.RenderTransform%2A> propiedad. Cada botón contiene texto. Inicialmente, el texto aparece el mismo en ambos botones, pero cuando se cambia el tamaño de los botones, el texto en el segundo botón deformado.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[transformanimations_snip#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/AnimatingSizeExample.xaml#1)]  
  
 Cuando se transforma un elemento, se transforma todo el elemento y su contenido. Cuando se modifica directamente el tamaño de un elemento, como en el caso del primer botón, el contenido del elemento no se cambia el tamaño a menos que su tamaño y posición dependen del tamaño de su elemento primario.  
  
 Animar el tamaño de un elemento aplicando una transformación animada a su <xref:System.Windows.UIElement.RenderTransform%2A> propiedad proporciona un mejor rendimiento que anima su <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> directamente, porque la <xref:System.Windows.UIElement.RenderTransform%2A> propiedad desencadenar un paso de diseño.  
  
 Para obtener más información sobre la animación de propiedades, vea la [información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). Para obtener más información acerca de las transformaciones, consulte el [Transforms Overview](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).
