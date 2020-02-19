---
title: 'Cómo: Controlar una animación mediante From, To y By'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], From/to/by
- basic animation [WPF]
- animation [WPF], basic animation
- From/to/by animation
ms.assetid: 59afba57-6fc1-44c8-987e-8a5f4142adad
ms.openlocfilehash: b06df97dc57c58a01f30be2d70bfeebf104521ad
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451790"
---
# <a name="how-to-control-an-animation-using-from-to-and-by"></a>Cómo: Controlar una animación mediante From, To y By
Una "from/to/by" o "Basic Animation" crea una transición entre dos valores de destino (consulte [información general sobre animaciones](animation-overview.md) para ver una introducción a los diferentes tipos de animaciones). Para establecer los valores de destino de una animación básica, utilice sus propiedades <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.  En la tabla siguiente se resume cómo se pueden usar las propiedades <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> juntas o por separado para determinar los valores de destino de una animación.  
  
|Propiedades especificadas|Comportamiento resultante|  
|--------------------------|------------------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>|La animación progresa desde el valor especificado por la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> hasta el valor base de la propiedad que se anima o hasta el valor de salida de una animación anterior, en función de cómo esté configurada la animación anterior.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> y <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|La animación progresa desde el valor especificado por la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> hasta el valor especificado por la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|La animación progresa desde el valor especificado por la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> hasta el valor especificado por la suma de las propiedades <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|La animación progresa desde el valor base de la propiedad animada o desde el valor de salida de una animación anterior hasta el valor especificado por la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|La animación progresa desde el valor base de la propiedad que se anima o desde el valor de salida de una animación previa hasta la suma de ese valor y el valor especificado por la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.|  
  
> [!NOTE]
> No establezca la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> y la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> en la misma animación.  
  
 Para usar otros métodos de interpolación o animar entre más de dos valores de destino, use una animación de fotogramas clave. Consulte información [General sobre animaciones de fotogramas clave](key-frame-animations-overview.md) para obtener más información.  
  
 Para obtener información sobre cómo aplicar varias animaciones a una sola propiedad, vea [información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md).  
  
 En el ejemplo siguiente se muestran los distintos efectos de establecer las propiedades <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>y <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> en las animaciones.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[BasicAnimations_snippet#AnimationTargetValuesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snippet/CS/AnimationTargetValuesExample.xaml#animationtargetvalueswholepage)]  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre animaciones](animation-overview.md)
- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
- [Ejemplo de valores de destino de animación From, To y By](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/TargetValues)
