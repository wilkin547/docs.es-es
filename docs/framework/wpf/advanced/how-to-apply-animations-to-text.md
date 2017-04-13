---
title: "C&#243;mo: Aplicar animaciones a texto | Microsoft Docs"
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
  - "animación, texto"
  - "tipografía, animaciones"
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Aplicar animaciones a texto
Las animaciones pueden modificar la presentación y el aspecto del texto de la aplicación.  En los ejemplos siguientes se utilizan tipos diferentes de animaciones para influir en la presentación del texto en un control <xref:System.Windows.Controls.TextBlock>.  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza un objeto <xref:System.Windows.Media.Animation.DoubleAnimation> para animar el ancho del bloque de texto.  El valor del ancho cambia del ancho del bloque de texto a 0 a lo largo de 10 segundos y, a continuación, se invierten los valores de ancho y se continúa.  Este tipo de animación crea un efecto de barrido.  
  
 [!code-xml[TextAnimationSample#TextAnimationSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 En el ejemplo siguiente se utiliza un objeto <xref:System.Windows.Media.Animation.DoubleAnimation> para animar la opacidad del bloque de texto.  El valor de opacidad cambia de 1,0 a 0 a lo largo de 5 segundos y, a continuación, se invierten los valores de opacidad y se continúa.  
  
 [!code-xml[TextAnimationSample#TextAnimationSample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 En el diagrama siguiente se muestra el efecto del control <xref:System.Windows.Controls.TextBlock> al cambiar su opacidad de `1.00` a `0.00` durante el intervalo de 5 segundos definido por la propiedad <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.  
  
 ![Texto cuya opacidad cambia de 1,00 a 0,00](../../../../docs/framework/wpf/advanced/media/fadedtext01.png "FadedText01")  
Cambio de la opacidad del texto de 1,00 a 0,00  
  
 En el ejemplo siguiente se utiliza <xref:System.Windows.Media.Animation.ColorAnimation> para animar el color de primer plano del bloque de texto.  El valor del color de primer plano cambia de un color a un segundo color a lo largo de 5 segundos y, a continuación, se invierten los valores de color y se continúa.  
  
 [!code-xml[TextAnimationSample#TextAnimationSample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 En el ejemplo siguiente se utiliza un objeto <xref:System.Windows.Media.Animation.DoubleAnimation> para girar el bloque de texto.  El bloque de texto realiza un giro completo a lo largo de 20 segundos y, a continuación, continúa repitiendo el giro.  
  
 [!code-xml[TextAnimationSample#TextAnimationSample4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## Vea también  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)