---
title: 'Cómo: Hacer que un elemento gire en su posición'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: a1b515822391de08ec8ed8ff0ff1f0086874dc02
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112081"
---
# <a name="how-to-make-an-element-spin-in-place"></a>Cómo: Hacer que un elemento gire en su posición
En este ejemplo se muestra cómo hacer <xref:System.Windows.Media.RotateTransform> que <xref:System.Windows.Media.Animation.DoubleAnimation>un elemento gire mediante un archivo y un archivo .  
  
 En el ejemplo <xref:System.Windows.Media.RotateTransform> siguiente <xref:System.Windows.UIElement.RenderTransform%2A> se aplica la propiedad del elemento. En el <xref:System.Windows.Media.Animation.DoubleAnimation> ejemplo se <xref:System.Windows.Media.RotateTransform.Angle%2A> utiliza <xref:System.Windows.Media.RotateTransform>a para animar el archivo . Para que el elemento gire en su <xref:System.Windows.UIElement.RenderTransformOrigin%2A> lugar, el ejemplo establece la propiedad del elemento en el punto (0.5, 0.5).  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 Para ver el ejemplo completo, que incluye más ejemplos de transformación, vea Ejemplo de [transformaciones 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre animaciones](animation-overview.md)
- [Información general sobre transformaciones](transforms-overview.md)
