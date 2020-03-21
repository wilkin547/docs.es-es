---
title: 'Cómo: Trasladar un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
ms.openlocfilehash: addff0e22fb3f27ea924887809c0635aeb3ad67d
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111977"
---
# <a name="how-to-translate-an-element"></a>Cómo: Trasladar un elemento
En este ejemplo se muestra cómo traducir <xref:System.Windows.Media.TranslateTransform>(mover) un elemento mediante un archivo .  
  
 La <xref:System.Windows.Media.TranslateTransform> clase es especialmente útil para mover elementos dentro de paneles que no admiten el posicionamiento absoluto. Por ejemplo, al <xref:System.Windows.Media.TranslateTransform> aplicar <xref:System.Windows.UIElement.RenderTransform%2A> a la propiedad de un elemento, <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Controls.DockPanel>puede mover un elemento dentro de un o .  
  
 Utilice <xref:System.Windows.Media.TranslateTransform.X%2A> la propiedad <xref:System.Windows.Media.TranslateTransform> de la para especificar la cantidad, en píxeles, para mover el elemento a lo largo del eje X. Utilice <xref:System.Windows.Media.TranslateTransform.Y%2A> la propiedad para especificar la cantidad, en píxeles, para mover el elemento a lo largo del eje Y. Por último, <xref:System.Windows.Media.TranslateTransform> aplique <xref:System.Windows.UIElement.RenderTransform%2A> la propiedad a la propiedad del elemento.  
  
 En el ejemplo <xref:System.Windows.Media.TranslateTransform> siguiente se usa a para mover un elemento 50 píxeles a la derecha y 50 píxeles hacia abajo.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[transformsSample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 Para ver el ejemplo completo, consulte Ejemplo de [transformaciones 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre transformaciones](transforms-overview.md)
