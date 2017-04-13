---
title: "C&#243;mo: Controlar un gui&#243;n gr&#225;fico una vez iniciado | Microsoft Docs"
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
  - "Guiones gráficos, controlar después del inicio"
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Controlar un gui&#243;n gr&#225;fico una vez iniciado
En este ejemplo se muestra cómo utilizar el código para controlar un objeto <xref:System.Windows.Media.Animation.Storyboard> después de iniciarse.  Para controlar un guión gráfico en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], utilice los objetos <xref:System.Windows.Trigger> y <xref:System.Windows.TriggerAction>; para obtener un ejemplo, vea [Utilizar desencadenadores de eventos para controlar un guión gráfico después de su inicio](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).  
  
 Para iniciar un guión gráfico, se utiliza su método <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>, que distribuye las animaciones del guión gráfico a las propiedades animadas por ellas, e inicia el guión gráfico.  
  
 Para poder controlar un guión gráfico, se utiliza el método <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> y se especifica **true** como segundo parámetro.  A continuación, puede utilizar los métodos interactivos del guión gráfico para pausar, reanudar, buscar, detener, acelerar o ralentizar el guión gráfico, o avanzarlo hasta su período del relleno.  A continuación, se muestra una lista de los métodos interactivos del guión gráfico:  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: pone en pausa el guión gráfico.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: reanuda un guión gráfico que se ha puesto en pausa.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: establece la velocidad interactiva del guión gráfico.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: busca en el guión gráfico la ubicación especificada.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: busca en el guión gráfico hasta la ubicación especificada.  A diferencia del método <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>, esta operación se procesa antes del paso siguiente.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: avanza un guión gráfico hasta su período de relleno, si lo tiene.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: detiene el guión gráfico.  
  
 En el ejemplo siguiente, se utilizan varios métodos de guión gráfico para controlar interactivamente un guión gráfico.  
  
 **Nota:** para ver un ejemplo de control de un guión gráfico mediante desencadenadores con [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], vea [Utilizar desencadenadores de eventos para controlar un guión gráfico después de su inicio](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).  
  
## Ejemplo  
 [!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
 [!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]  
  
## Vea también  
 [Utilizar desencadenadores de eventos para controlar un guión gráfico después de su inicio](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)