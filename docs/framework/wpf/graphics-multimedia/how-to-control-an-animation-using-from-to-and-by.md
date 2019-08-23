---
title: Procedimiento Controlar una animación mediante From, To y By
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], From/to/by
- basic animation [WPF]
- animation [WPF], basic animation
- From/to/by animation
ms.assetid: 59afba57-6fc1-44c8-987e-8a5f4142adad
ms.openlocfilehash: 812217a2905671567271687b974a435dd85cea47
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930086"
---
# <a name="how-to-control-an-animation-using-from-to-and-by"></a>Procedimiento Controlar una animación mediante From, To y By
Una "from/to/by" o "Basic Animation" crea una transición entre dos valores de destino (consulte [información general sobre animaciones](animation-overview.md) para ver una introducción a los diferentes tipos de animaciones). Para establecer los valores de destino de una animación básica, utilice <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>sus <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>propiedades, <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> y.  En la tabla siguiente se resume <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>cómo <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>se pueden <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> usar las propiedades, y juntas o por separado para determinar los valores de destino de una animación.  
  
|Propiedades especificadas|Comportamiento resultante|  
|--------------------------|------------------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>|La animación progresa desde el valor especificado por la <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedad hasta el valor base de la propiedad que se anima o hasta el valor de salida de una animación anterior, en función de cómo esté configurada la animación anterior.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> y <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|La animación progresa desde el valor especificado por la <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedad hasta el valor especificado por la <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> propiedad.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|La animación progresa desde el valor especificado por la <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedad hasta el valor especificado por la suma de las <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedades y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> .|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|La animación progresa desde el valor base de la propiedad animada o desde el valor de salida de una animación anterior hasta el valor <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> especificado por la propiedad.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|La animación progresa desde el valor base de la propiedad que se anima o desde el valor de salida de una animación previa hasta la suma de ese valor y el valor <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> especificado por la propiedad.|  
  
> [!NOTE]
> No establezca la <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> propiedad y la <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedad en la misma animación.  
  
 Para usar otros métodos de interpolación o animar entre más de dos valores de destino, use una animación de fotogramas clave. Consulte información [General sobre animaciones](key-frame-animations-overview.md) de fotogramas clave para obtener más información.  
  
 Para obtener información sobre cómo aplicar varias animaciones a una sola propiedad, vea [información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md).  
  
 En el ejemplo siguiente se muestran los distintos efectos <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>de <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>establecer las <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedades, y en las animaciones.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[BasicAnimations_snippet#AnimationTargetValuesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snippet/CS/AnimationTargetValuesExample.xaml#animationtargetvalueswholepage)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre animaciones](animation-overview.md)
- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
- [Ejemplo de valores de destino de animación From, To y By](https://go.microsoft.com/fwlink/?LinkID=159988)
