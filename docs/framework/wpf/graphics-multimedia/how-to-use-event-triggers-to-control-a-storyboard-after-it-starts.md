---
title: "C&#243;mo: Utilizar desencadenadores de eventos para controlar un gui&#243;n gr&#225;fico despu&#233;s de su inicio | Microsoft Docs"
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
  - "desencadenadores de eventos, controlar guiones gráficos"
  - "Guiones gráficos, controlar después del inicio"
  - "desencadenadores, controlar guiones gráficos"
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# C&#243;mo: Utilizar desencadenadores de eventos para controlar un gui&#243;n gr&#225;fico despu&#233;s de su inicio
En este ejemplo se muestra cómo controlar un objeto <xref:System.Windows.Media.Animation.Storyboard> después de iniciarse.  Para iniciar un objeto <xref:System.Windows.Media.Animation.Storyboard> mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], utilice <xref:System.Windows.Media.Animation.BeginStoryboard>, que distribuye las animaciones a los objetos y las propiedades que se animan y, a continuación, inicia el guión gráfico.  Si asigna un nombre a <xref:System.Windows.Media.Animation.BeginStoryboard> especificando su propiedad <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A>, lo convierte en un guión gráfico controlable.  A continuación, podrá controlar interactivamente el guión gráfico una vez iniciado.  
  
 Utilice las acciones de guión gráfico siguientes junto con objetos <xref:System.Windows.EventTrigger> para controlar un guión gráfico.  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard>: pone en pausa el guión gráfico.  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard>: reanuda un guión gráfico que se ha puesto en pausa.  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: cambia la velocidad del guión gráfico.  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: avanza un guión gráfico hasta el final de su período de relleno, si lo tiene.  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard>: detiene el guión gráfico.  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard>: quita el guión gráfico para liberar recursos.  
  
## Ejemplo  
 En el ejemplo siguiente se utilizan acciones para controlar interactivamente un guión gráfico.  
  
 **Nota:** para ver un ejemplo de control de un guión gráfico mediante código, vea [Controlar un guión gráfico una vez iniciado usando métodos interactivos](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md).  
  
 [!code-xml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 Para obtener ejemplos adicionales, vea [Animation Example Gallery](http://go.microsoft.com/fwlink/?LinkID=159969).  
  
## Vea también  
 <xref:System.Windows.Media.Animation.ResumeStoryboard>   
 <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>   
 <xref:System.Windows.Media.Animation.SkipStoryboardToFill>   
 <xref:System.Windows.Media.Animation.PauseStoryboard>   
 <xref:System.Windows.Media.Animation.StopStoryboard>   
 <xref:System.Windows.Media.Animation.SeekStoryboard>   
 [Controlar un guión gráfico una vez iniciado usando métodos interactivos](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md)   
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Información general sobre objetos Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)