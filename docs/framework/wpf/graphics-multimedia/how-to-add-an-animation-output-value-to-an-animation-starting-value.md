---
title: Procedimiento Agregar un valor de salida de animación a un valor inicial de animación
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF]
ms.assetid: b89a82be-b03d-481e-a8d3-cc513d09ca00
ms.openlocfilehash: 945675d03a280e2394fdb0eab27c0978dc7cc320
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010246"
---
# <a name="how-to-add-an-animation-output-value-to-an-animation-starting-value"></a>Procedimiento Agregar un valor de salida de animación a un valor inicial de animación
En este ejemplo se muestra cómo agregar un valor de salida de animación a un valor inicial de animación.  
  
## <a name="example"></a>Ejemplo  
 El <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> propiedad especifica si desea que el valor de salida de una animación que se agrega al valor inicial (valor base) de una propiedad animada. Puede usar el <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> propiedad con animaciones más básicas y la mayoría de las animaciones de fotogramas clave. Para obtener más información, consulte [información general sobre animaciones](animation-overview.md) y [información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md).  
  
 El ejemplo siguiente muestra el efecto de usar el <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> propiedad con <xref:System.Windows.Media.Animation.DoubleAnimation> y el uso de la <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> propiedad con <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.  
  
 [!code-xaml[timingbehaviors_snip#IsAdditiveWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsAdditiveExample.xaml#isadditivewholepage)]  
  
## <a name="see-also"></a>Vea también

- [Acumular valores de animaciones durante la repetición de ciclos](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [Información general sobre animaciones](animation-overview.md)
- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
- [Temas de procedimientos de temporización y animación](animation-and-timing-how-to-topics.md)
