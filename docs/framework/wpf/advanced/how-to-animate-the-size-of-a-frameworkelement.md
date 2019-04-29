---
title: Procedimiento Animar el tamaño de un elemento FrameworkElement
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], FrameworkElement size
- FrameworkElement [WPF], animating size of
ms.assetid: d4cd5a13-c20d-4a6f-a2ba-14f2c9ce4cef
ms.openlocfilehash: d1995deec5ab2c9bf405911af43b4d242d599119
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776914"
---
# <a name="how-to-animate-the-size-of-a-frameworkelement"></a>Procedimiento Animar el tamaño de un elemento FrameworkElement
Para animar el tamaño de un <xref:System.Windows.FrameworkElement>, o bien puede animar su <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades o use un elemento animado <xref:System.Windows.Media.ScaleTransform>.  
  
 En el ejemplo siguiente anima el tamaño de dos botones con estos dos enfoques. Se cambia el tamaño de un botón, animando su <xref:System.Windows.FrameworkElement.Width%2A> cambia el tamaño de propiedad y otro animando un <xref:System.Windows.Media.ScaleTransform> aplicado a su <xref:System.Windows.UIElement.RenderTransform%2A> propiedad. Cada botón contiene texto. Inicialmente, el texto aparece en la misma en ambos botones, pero cuando se cambia el tamaño de los botones, el texto en el segundo botón se distorsiona.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[transformanimations_snip#1](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/AnimatingSizeExample.xaml#1)]  
  
 Al transformar un elemento, se transforma todo el elemento y su contenido. Cuando se modifica directamente el tamaño de un elemento, como en el caso del primer botón, no se cambia el tamaño del contenido del elemento a menos que su tamaño y posición dependen del tamaño de su elemento primario.  
  
 Animar el tamaño de un elemento aplicando una transformación animada a su <xref:System.Windows.UIElement.RenderTransform%2A> propiedad proporciona un mejor rendimiento que anima su <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> directamente, porque el <xref:System.Windows.UIElement.RenderTransform%2A> propiedad desencadenar una fase de diseño.  
  
 Para obtener más información acerca de cómo animar propiedades, vea el [información general sobre animaciones](../graphics-multimedia/animation-overview.md). Para obtener más información acerca de las transformaciones, vea el [información general sobre transformaciones](../graphics-multimedia/transforms-overview.md).
