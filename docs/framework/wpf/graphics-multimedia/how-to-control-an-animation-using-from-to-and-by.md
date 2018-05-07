---
title: 'Cómo: Controlar una animación mediante From, To y By'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], From/to/by
- basic animation [WPF]
- animation [WPF], basic animation
- From/to/by animation
ms.assetid: 59afba57-6fc1-44c8-987e-8a5f4142adad
ms.openlocfilehash: c6f2bfb207163136d79e815e7f910673e8fafade
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-control-an-animation-using-from-to-and-by"></a>Cómo: Controlar una animación mediante From, To y By
Un "From/To/By" o "animación básica" crea una transición entre dos valores de destino (vea [información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) para obtener una introducción a distintos tipos de animaciones). Para establecer los valores de destino de una animación básica, use su <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedades.  La tabla siguiente resume cómo el <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedades se pueden utilizar conjuntamente o por separado los valores determinar el destino de una animación.  
  
|Propiedades especificadas|Comportamiento resultante|  
|--------------------------|------------------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>|La animación progresa desde el valor especificado por el <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> valor, según cómo esté configurada la animación anterior de salida de propiedad al valor base de la propiedad que se está animando o a una animación anterior.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> y <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|La animación progresa desde el valor especificado por el <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedad en el valor especificado por el <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> propiedad.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|La animación progresa desde el valor especificado por el <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedad en el valor especificado por la suma de la <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedades.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|La animación progresa desde el valor base de la propiedad animada o una animación anterior de salida de valor para el valor especificado por el <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> propiedad.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|La animación progresa desde el valor base de la propiedad que se está animando o una animación anterior del valor de salida a la suma de ese valor y el valor especificado por el <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedad.|  
  
> [!NOTE]
>  No establezca la <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> propiedad y el <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedad en la misma animación.  
  
 Para usar otros métodos de interpolación o animar entre más de dos valores de destino, use una animación de fotogramas clave. Vea [información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md) para obtener más información.  
  
 Para obtener información sobre cómo aplicar varias animaciones a una sola propiedad, vea [información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
 El ejemplo siguiente muestra los efectos diferentes del valor <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>, y <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedades en las animaciones.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[BasicAnimations_snippet#AnimationTargetValuesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snippet/CS/AnimationTargetValuesExample.xaml#animationtargetvalueswholepage)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Ejemplo de valores de destino de animación From, To y By](http://go.microsoft.com/fwlink/?LinkID=159988)
