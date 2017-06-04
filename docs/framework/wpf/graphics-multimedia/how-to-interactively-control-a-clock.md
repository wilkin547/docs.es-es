---
title: "C&#243;mo: Controlar interactivamente un reloj | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "relojes, controlar interactivamente"
  - "controlar relojes interactivamente"
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# C&#243;mo: Controlar interactivamente un reloj
La propiedad <xref:System.Windows.Media.Animation.ClockController> de un objeto <xref:System.Windows.Media.Animation.Clock> permite iniciar, pausar, reanudar, buscar y avanzar interactivamente el reloj hasta su período del relleno y detenerlo.  Únicamente se puede controlar interactivamente el reloj raíz de un árbol de control de tiempo.  
  
> [!NOTE]
>  Hay otras maneras de controlar interactivamente las animaciones que no exigen que se trabaje directamente con relojes: también puede utilizar guiones gráficos.  Los guiones gráficos se admiten en el marcado y en el código.  Para obtener un ejemplo, vea [Animar una propiedad utilizando un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) o [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 En el ejemplo siguiente, se utilizan varios botones para controlar interactivamente un reloj de animación.  
  
## Ejemplo  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## Vea también  
 [Animar una propiedad utilizando un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)   
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)