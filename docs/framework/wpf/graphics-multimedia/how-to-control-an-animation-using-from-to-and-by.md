---
title: "C&#243;mo: Controlar una animaci&#243;n mediante From, To y By | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "animación de/a/by"
  - "animación básica"
  - "animación, animación básica"
  - "From/To/By (animación)"
ms.assetid: 59afba57-6fc1-44c8-987e-8a5f4142adad
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Controlar una animaci&#243;n mediante From, To y By
Un "From/To/By" o "animación básica" crea una transición entre dos valores de destino (consulte [información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) para obtener una introducción a distintos tipos de animaciones). Para establecer los valores de destino de una animación básica, use su <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedades.  La tabla siguiente resume cómo el <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedades se pueden utilizar conjuntamente o por separado los valores determinar el destino de una animación.  
  
|Propiedades especificadas|Comportamiento resultante|  
|--------------------------|------------------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>|La animación progresa desde el valor especificado por el <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> el valor, según cómo esté configurada la animación anterior de salida de propiedad para el valor base de la propiedad animada o una animación anterior.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> and                              <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|La animación progresa desde el valor especificado por el <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedad en el valor especificado por el <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> propiedad.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> and                              <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|La animación progresa desde el valor especificado por el <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedad en el valor especificado por la suma de la <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedades.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|La animación progresa desde el valor de la base de la propiedad animada o al valor especificado por el resultado de una animación anterior la <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> propiedad.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|La animación progresa desde el valor base de la propiedad animada o una animación anterior del valor de salida a la suma de ese valor y el valor especificado por el <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedad.|  
  
> [!NOTE]
>  No establezca la <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> propiedad y el <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedad en la misma animación.  
  
 Para usar otros métodos de interpolación o animar entre más de dos valores de destino, use una animación de fotogramas clave. Consulte [información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md) para obtener más información.  
  
 Para obtener información sobre cómo aplicar varias animaciones a una sola propiedad, vea [información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
 El ejemplo siguiente muestra los distintos efectos de configuración <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>, y <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedades de animaciones.  
  
## <a name="example"></a>Ejemplo  
 [!code-xml[BasicAnimations_snippet#AnimationTargetValuesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snippet/CS/AnimationTargetValuesExample.xaml#animationtargetvalueswholepage)]  
  
## <a name="see-also"></a>Vea también  
 [Información general de animación](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Desde, para y ejemplo de valores de destino de animación](http://go.microsoft.com/fwlink/?LinkID=159988)