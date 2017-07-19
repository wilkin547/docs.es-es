---
title: "C&#243;mo: Cambiar la velocidad de un reloj sin cambiar la velocidad de su escala de tiempo | Microsoft Docs"
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
  - "relojes, cambiar la velocidad de"
  - "velocidad de Clock, cambiar"
ms.assetid: 72f36dd0-f085-445d-8589-19a83fe74f5e
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# C&#243;mo: Cambiar la velocidad de un reloj sin cambiar la velocidad de su escala de tiempo
La propiedad <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> de un objeto <xref:System.Windows.Media.Animation.ClockController> permite cambiar la velocidad de un objeto <xref:System.Windows.Media.Animation.Clock> sin modificar la propiedad <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> de la escala de tiempo \(<xref:System.Windows.Media.Animation.Timeline>\) del reloj.  En el ejemplo siguiente, se utiliza un controlador <xref:System.Windows.Media.Animation.ClockController> para modificar interactivamente la propiedad <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> de un reloj.  El evento <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> y la propiedad <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> del reloj se utilizan para mostrar la velocidad global actual del reloj cada vez que se cambia su <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> interactiva.  
  
## Ejemplo  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerSpeedRatioExample.cs#graphicsmmclockcontrollerspeedratioexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerspeedratioexample.vb#graphicsmmclockcontrollerspeedratioexample)]