---
title: 'Cómo: Hacer que un elemento gire en su posición'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: 2e72389a11e48629c2763fcbd9f7b1945ffff5dd
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452797"
---
# <a name="how-to-make-an-element-spin-in-place"></a>Cómo: Hacer que un elemento gire en su posición
En este ejemplo se muestra cómo hacer que un elemento gire mediante un <xref:System.Windows.Media.RotateTransform> y un <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
 En el ejemplo siguiente se aplica el <xref:System.Windows.Media.RotateTransform> a la propiedad <xref:System.Windows.UIElement.RenderTransform%2A> del elemento. En el ejemplo se usa un <xref:System.Windows.Media.Animation.DoubleAnimation> para animar el <xref:System.Windows.Media.RotateTransform.Angle%2A> de la <xref:System.Windows.Media.RotateTransform>. Para hacer que el elemento gire en su lugar, en el ejemplo se establece la propiedad <xref:System.Windows.UIElement.RenderTransformOrigin%2A> del elemento en el punto (0,5, 0,5).  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 Para obtener el ejemplo completo, que incluye más ejemplos de transformación, vea [ejemplo de transformaciones 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre animaciones](animation-overview.md)
- [Información general sobre transformaciones](transforms-overview.md)
